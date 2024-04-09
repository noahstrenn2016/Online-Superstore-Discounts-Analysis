This SQL query returns the 

Here is the SQL query:

```sql
select distinct a.customername,
		sum(b.amount) as total_sales,
		(case 
			when sum(b.amount) >= 5000 then 'Platinum'
			when sum(b.amount) >= 2500 and sum(b.amount) <= 4999 then 'Gold'
			when sum(b.amount) >= 500 and sum(b.amount) <= 2499 then 'Silver'
			else 'Standard'
		end) as membership_level
from 
    list_of_orders a 
inner join 
    order_details b on a.order_id = b.order_id
group by 
    a.customername
order by 
    sum(b.amount) desc
```


    
