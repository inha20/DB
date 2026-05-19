# 프로시져

<details><summary>문법
</summary>
➜ price decimal(10,2) ; // 화폐. 10자리까지, 소수점 2째자리까지.<br>
➜ <br>
➜ <br>
➜ <br>
</details>

<details><summary>주요문법
</summary>
```mysql
delimiter // 
create procedure usp_insert_product(
	in p_id char(8),
    in p_name varchar(100),
    in p_price decimal(10,2),
    in p_quantity int
)
begin 
	insert into product (id, name, price, quantity)
    values (p_id, p_name, p_price, p_quantity);
end //
delimiter ;
  ```
</details>
