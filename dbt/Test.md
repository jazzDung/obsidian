## Các loại test
- Singular test
	- Mình tự tạo logic để test
- General test
	- Unique
	- Not null
	- Accepted values
	- Relationships
	- Ngoài ra có thể import bằng package hoặc tự viết custom test
- Test sẽ làm gì?
	- 

## Generic test

```bash
version: 2

models:
  - name: stg_customers
    columns: 
      - name: customer_id
        tests:
          - unique
          - not_null
  - name: stg_orders
    columns: 
      - name: order_id
        tests:
          - unique
          - not_null
          
      - name: status
        tests:
          - accepted_values:
              values:
                - completed
                - shipped
                - returned
                - placed
                - return_pending
                
      - name: customer_id
        tests:
          - relationships:
              to: ref('stg_customers')
              field: customer_id
```

## Singular test
- Tạo file SQL để select record KHÔNG thỏa mãn điều kiện cần test
- Để nó vào folder models/tests

```sql
-- Refunds have a negative amount, so the total amount should always be >= 0.
-- Therefore return records where this isn't true to make the test fail.
select
    order_id,
    sum(amount) as total_amount
from {{ ref('stg_payments') }}
group by 1
having not(total_amount >= 0)
```


## Source testing
