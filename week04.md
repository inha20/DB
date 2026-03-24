 # 2 sheet

> JOIN문

<details><summary>
선행1
</summary>
	
```SQL

use class_a;

```

</details>



<details><summary>
선행2
</summary>

```SQL

create table dbstudent (
	department varchar(50) not null,
    student_number INT primary key,
    name varchar(20) not null,
    grade int,
    cell_phone varchar(20),
    email varchar(50)
);
```
</details>




<details><summary>
선행3
</summary>
	
```SQL
	
insert into dbstudent (department, student_number, name, grade,  cell_phone, email) 
values	('정보통신공학과', 202633024, '김태우', 1, '010-2487-4727', 'qustkd@naver.com'),
	('컴퓨터정보공학과', 202533027, '조은호', 2, '010-9048-0317', 'ehcho@hanmail.net'),
	('컴퓨터정보공학과', 202433006, '황정하', 3, '010-3606-4256', 'jhh@naver.com'),
	('컴퓨터정보공학과', 202533039, '최진영', 1, null, 'jychoi@naver.com'),
	('컴퓨터정보공학과', 202533033, '이상선', 2, '010-1487-4770', 'sslee@naver.com'),
	('컴퓨터정보공학과', 202433026, '박주봉', 3, '010-0048-0312', 'kbpark@hanmail.net'),
	('정보통신공학과', 202633007, '이지은', 1, '010-5606-4251', 'jelee@naver.com'),
	('정보통신공학과', 202533022, '김동주', 2, null, 'djkim@naver.com'),
	('컴퓨터시스템공학과', 202433019, '박성수', 3, '010-x487-4722', 'sspark@naver.com'),
	('디지털마케팅공학과', 202533012, '김아름', 2, '010-2048-0307', 'alkim@hanmail.net'),
	('전기공학과', 202533002, '최진기', 2, '010-8606-4151', 'jkchoi@naver.com'),
	('항공운항과', 202633038, '허준', 2, null, 'jh01@naver.com');
	
```
</details>





<details><summary>
조작
</summary>
-- 주석 <br>
ctrl / 다중주석
</details>

<details><summary> SELECT * FROM dbstudents (WHERE 조건)

</summary>
➜ dbstudents 테이블의 조건에 맞는 모든 행과 모든 컬럼을 반환합니다.<br>
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


