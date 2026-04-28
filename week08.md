# 시트 만들기
> 변경하기
<details><summary>키워드
</summary>
➜ user_id int auto_increment primary key ; // 자동 증가.<br>
➜ alter table user add gender char(1) after name; // 테이블에 칼럼 추가.<br>
➜ alter table user change phone phone_number varchar(20); // 칼럼명, 형식 변경.<br>
➜ alter table user change gender gender enum("M", "F"); // 형식 변경 - 항목 제한.<br>
➜ drop table user; truncate table user; // 삭제하기, 내용 버리기.<br>
</details>
