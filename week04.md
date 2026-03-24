 # 2 sheet

> JOIN문

<details><summary>
JOIN과 테이블
</summary>	
➜ 공통 칼럼으로 연결하는 것. 이름이 달라도 되지만 Typs과 Size는 같아야됨.<br>
➜ 내부,외부,풀,재귀 의 종류가 있음. 기본값은 내부join.<br>
</details>



<details><summary>
선행
</summary>

```SQL
create table division (
	division_code char(4) primary key,
    division_name varchar(30)
);

create table employee (
	emp_no int auto_increment primary key,
    emp_name varchar(30),
    division_code char(4),
    emp_position varchar(30)
);
```
</details>




<details><summary>
복습
</summary>
	
```SQL
	
insert into employee (emp_name, division_code, emp_position) values 
	('홍길동', "1111","사원"), ("이기자","1111", "과장"), ("최전식", "1112", "부장"),
    ("강감찬", "1112", "대리"), ("이아름", "1113", "부장"), ("김소연", "1113", "차장");
	
```
</details>





<details><summary>
SELECT (a. , b. , a. ) FROM division a INNER JOIN employee b ON (JOIN조건) where (검색조건);
</summary>
SELECT a.division_name, b.emp_name, b.emp_position FROM division a INNER JOIN employee b ON a.division_code=b.division_code where a.division_code="1112";
</details>

<details><summary> 
SELECT (a. , b. , a. ) FROM division a LEFT OUTER JOIN employee b ON (JOIN조건) where (검색조건);
</summary>
SELECT * FROM division a LEFT OUTER JOIN employee b ON a.division_code=b.division_code;
</details>

LEFT JOIN UNION RIGHT JOIN 하면 FULL JOIN.



> SubQuery
