# SELECT문
> 1회기
<details><summary> SELECT * FROM dbstudents (WHERE 조건)

</summary>
➜ dbstudents 테이블의 조건에 맞는 모든 행과 모든 컬럼을 반환합니다.<br>
<table>
<thead><tr><th>연산자</th><th>설명</th></tr></thead>
<tbody><tr><td>>=, <>, !=, !<</td><td></td></tr>
        <tr><td>AND, OR, NOT</td><td></td></tr>
        <tr><td>BETWEEN</td><td>BETWEEN a AND b</td></tr>
        <tr><td>LIKE</td><td>'김%'</td></tr>
        <tr><td>IN</td><td>IN(1,3) !=2</td></tr>
        <tr><td>EXISTS</td><td></td></tr>
        <tr><td>IS NULL</td><td></td></tr>
</tbody>
</table>
</details>
<details><summary>
SELECT 칼럼명 AS [새 칼럼명], 칼럼명 AS [새 칼럼명] (WHERE 조건)
</summary>
FROM 생략은 하나의 셀 안에서만
</details>

<details><summary>
SELECT 칼럼명 (WHERE 조건) ORDER BY 정렬칼럼명 DESC
</summary>
ASC
</details>


<details><summary>
SELECT 칼럼명 (WHERE 조건) GROUP BY SELECT 분류기준
</summary>
SELECT grade AS 학년, count(*) AS 학생수 
FROM dbstudents 
GROUP BY grade
</details>



