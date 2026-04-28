# 무결성 이어서
> 범위
<details><summary>check
</summary>
➜ age int check (age >= 19) ; // 칼럼 수준의 제약조건<br>
➜ constraint chk_quantity check (quantity >= 1)<br>
➜ constraint chk_delivery_date check (delivery_date >= order_date); // 테이블 수준.<br>
➜ constraint chk_status check (status in ("ready","shipping","delivered","cancelled"))<br>
</details>

<details><summary>default
</summary>
➜ quantity int not null default 1<br>
➜ order_status varchar(20) default "pending"<br>
➜ ordered_at datetime default now()<br>
