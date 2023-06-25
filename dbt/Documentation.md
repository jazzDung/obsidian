## Các loại document
1. DAG
	- DAG tự tạo bằng cách dùng ref trong model
2. Document cho từng model
	- Document ngay tại yml tương ứng với model
	- Hoặc dùng doc block

## Document trong yml
```yml
version: 2

models:
  - name: stg_customers
	# Description for table
    description: one unique customer per row 
    columns: 
      - name: customer_id
	    # Description for column
        description: primary key for stg_customers 
        tests:
          - unique
          - not_null
```

```yml
version: 2

models:
      - name: status
	    # Description from doc block 
        description: '{{ doc("order_status") }}' 
        tests:
          - accepted_values:
              values:
                - completed
                - shipped
                - returned
                - placed
                - return_pending
```

## Doc block

```md
{% docs order_status %}
[comment]: <This is the name used for reference in yml file, not the md file name>
	
One of the following values: 

| status         | definition                                       |
|----------------|--------------------------------------------------|
| placed         | Order placed, not yet shipped                    |
| shipped        | Order has been shipped, not yet been delivered   |
| completed      | Order has been received by customers             |
| return pending | Customer indicated they want to return this item |
| returned       | Item has been returned                           |

{% enddocs %}
```

**Result:**
![[Pasted image 20230411190654.png]]