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
➜ priority tinyint default 0, <br>
➜ order_status varchar(20) default "pending"<br>
➜ ordered_at datetime default now()<br>
➜ quantity int not null default 1<br>
</details>

<details><summary>foreign key(외래키:자식 테이블)
</summary>
➜ constraint pk_noOptBuseo_buseocode primary key (busecode)<br>
➜ constraint fk_noOptSawon_buseocode foreign key(buseocode) references noOtpBuseo(busecode)<br>
➜ on delete cascade ; // 부모가 사라지면 자식도 같이 사라짐
➜ on update cascade ; // 부모가 변경 자식도 같이 변경됨
</details>
