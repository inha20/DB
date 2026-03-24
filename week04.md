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
SELECT * 
FROM division a 
LEFT OUTER JOIN employee b 
	ON a.division_code=b.division_code;
<table>
<thead><tr><th>연산자</th><th>설명</th></tr></thead>
<tbody><tr><td>>=, <>, !=, !<</td><td>NULL은 못찾아</td></tr>
        <tr><td>AND, OR, NOT</td><td></td></tr>
        <tr><td>BETWEEN</td><td>BETWEEN a AND b</td></tr>
        <tr><td>LIKE</td><td>'김%', '%hanmail.net'</td></tr>
        <tr><td>IN</td><td>IN(1,3)&nbsp;&nbsp;&nbsp;&nbsp;!=2</td></tr>
        <tr><td>EXISTS</td><td></td></tr>
        <tr><td>IS NULL</td><td></td></tr>
</tbody>
</table>
➜ SELECT avg.grade ; // max, min <br>
</details>
<details><summary>
SELECT 칼럼명 AS 새칼럼명, 칼럼명 AS 새칼럼명 FROM dbstudents (WHERE 조건)
</summary>
FROM 생략은 하나의 셀 안에서도 불가.
</details>

<details><summary>
SELECT 칼럼명 FROM dbstudents (WHERE 조건)  ORDER BY 정렬칼럼명 DESC
</summary>
ASC
</details>


<details><summary>
SELECT 칼럼명 FROM dbstudents (WHERE 조건) GROUP BY SELECT 분류기준
</summary>
SELECT grade AS 학년, count(*) AS 학생수 
FROM dbstudents 
GROUP BY grade
</details>


<details><summary>
SELECT 칼럼명 FROM dbstudents (WHERE 조건) GROUP BY SELECT 분류기준 ORDER BY 정렬칼럼명
</summary>
SELECT grade AS 학년, count(*) AS 학생수 
FROM dbstudents 
GROUP BY grade
</details>



> SubQuery


INSERT INTO dbstudent2 VALUES ( , , , , );


INSERT INTO dbstudent2 ( , , , , ) VALUES ( , , , , );


INSERT INTO dbstudent2 ( , , , , ) VALUES ( , , , , ),  ( , , , , ),  ( , , , , );


<details><summary>
INSERT INTO dbstudent2 ( , , , , ) SELECT ( , , , , ) FROM dbstudent WHERE 조건;
</summary>
select문에서 검색한 것을 insert로 복제한다. <br>
더 작게 복제할 때 쓴다. 더 크게는 쓰레기값 땜에 안함.
</details>


<details><summary>
DB 핸들링
</summary>
이후 파라미터 조작에서 values ?, ?, ? 으로 작성 후 반복문으로 DB에 데이터 넣음.
</details>



> UPDATE문


<details><summary>
UPDATE 테이블명 SET 칼럼1=값1, 칼럼2=값2 WHERE 조건;
</summary>
select * from dbstudent where student_number="202433019"; // primary key로 하나만 조회 먼저<br>
UPDATE dbstudent SET cell_phone="010-3487-4722" WHERE student_number="202433019";
</details>
<details><summary>
추가설정
</summary>
톱니바퀴 - SQL Editor - Safe Updates 해제 - 재접속 <br>
set sql_safe_updates =0;<br>
단순 변경은 상관없어, null값 왔다갔다는 필요.
</details>


> DELETE문

<details><summary>
DELETE FROM 테이블명 WHERE 조건;
</summary>
select * from dbstudent where grade=3; <br>
delete from dbstudent where grade=3;
</details>


