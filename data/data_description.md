# Описание данных для проекта анализа микрокредитной организации

В этой папке хранятся три основных файла с данными, используемыми для анализа кредитных заявок и платежей.

---

## 1. orders.csv  
Файл с информацией о заявках на микрокредиты.

| Колонка    | Тип       | Описание                                   |
|------------|-----------|--------------------------------------------|
| order_id   | int       | Уникальный идентификатор заявки            |
| created_at | datetime  | Дата и время создания заявки               |
| put_at     | datetime  | Дата и время выдачи кредита                |
| closed_at  | datetime  | Дата и время закрытия заявки               |
| issued_sum | float     | Сумма выданного кредита                    |

---

## 2. payments.csv  
Файл с информацией о фактических платежах по заявкам.

| Колонка  | Тип       | Описание                                     |
|----------|-----------|----------------------------------------------|
| order_id | int       | Идентификатор заявки, с которой связан платеж|
| paid_at  | datetime  | Дата и время фактического платежа            |
| paid_sum | float     | Сумма фактического платежа                   |

---

## 3. plan.csv  
Файл с плановыми платежами, связывает заявки и фактические платежи.

| Колонка       | Тип       | Описание                                  |
|---------------|-----------|-------------------------------------------|
| order_id      | int       | Идентификатор заявки                      |
| plan_at       | datetime  | Дата и время планового платежа            |
| plan_sum_total| float     | Накопленная сумма плановых платежей (итог)|

---

### Примечания  
- Все даты и времена приведены в едином формате ISO 8601 (YYYY-MM-DD HH:MM:SS).  
- `order_id` является ключом для связывания данных между файлами.  
- `plan_sum_total` — это накопленная сумма платежей, запланированных к определённой дате.  
