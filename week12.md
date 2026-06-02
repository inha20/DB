# 프로시져

<details><summary>문법
</summary>
➜ price decimal(10,2) ; // 화폐. 10자리까지, 소수점 2째자리까지.<br>
➜ call usp_insert_product("ep000003", "구글 픽셀 10a", 660000,1);<br>
➜ select * from product where name like concat ( '%',p_name, '%');<br>
➜ update product set quantity=quantity+deltaQuantity where id=p_id;<br>
➜ delete from product where id=p_id;
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

```mysql
delimiter // 
create procedure usp_add_product(
in p_id char(8),
in p_name varchar(100),
in p_price decimal(10,2),
in p_quantity int
)
begin
	declare exit handler for 1062
    begin
		select "이미 존재하는 id입니다. 삽입을 취소합니다." as Message;
	END;
    
    insert into product (id, name, price, quantity)
    values (p_id, p_name, p_price, p_quantity);
    select "제품이 성공적으로 추가되었습니다." as result;
END //
delimiter ;
```
</details>

# 뷰

<details><summary>문법
</summary>
➜ price decimal(10,2) ; // 화폐. 10자리까지, 소수점 2째자리까지.<br>
➜ call usp_insert_product("ep000003", "구글 픽셀 10a", 660000,1);<br>
➜ select * from product where name like concat ( '%',p_name, '%');<br>
➜ update product set quantity=quantity+deltaQuantity where id=p_id;<br>
➜ delete from product where id=p_id;
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

```mysql
delimiter // 
create procedure usp_add_product(
in p_id char(8),
in p_name varchar(100),
in p_price decimal(10,2),
in p_quantity int
)
begin
	declare exit handler for 1062
    begin
		select "이미 존재하는 id입니다. 삽입을 취소합니다." as Message;
	END;
    
    insert into product (id, name, price, quantity)
    values (p_id, p_name, p_price, p_quantity);
    select "제품이 성공적으로 추가되었습니다." as result;
END //
delimiter ;
```
</details>

