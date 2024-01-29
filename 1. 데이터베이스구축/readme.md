# 1. 다음 조건을 만족하는 테이블 스페이스를 생성하는 쿼리문을 작성하시오. (5점)
    1) 테이블 스페이스 이름 : user_exam

    2) 데이터 파일 이름 : C:/Exam/user_exam.dbf

    3) 용량 : 10MB

## 정답
```sql
CREATE TABLESPACE user_exam DATAFILE 'C:/Exam/user_exam.dbf' SIZE 10M;
```

# 2. 생성된 테이블 스페이스를 확인하기 위해서 테이블 스페이스의 목록을 조회할 수 있는 쿼리문을 작성하시오. (5점)
```sql
SELECT * FROM dba_tablespaces;
SELECT * FROM user_tablespaces;
```

# 3. 사용자 ID : joe 비밀번호 : black 기본 tablespace hr_data01 temporary tablespace temp인 사용자를 생성하는 명령어를 작성하시오(5점)
```sql
create user joe identified by black default tablespace hr_data01 temporary tablespace temp;
```

# 4. 다음의 제시한 내용을 보고 테이블을 만드는 명령문을 작성하시오.(5점)
```
 테이블 이름:employees_demo
 각 속성이름 및 데이터형 : employee_id NUMBER(6), last_name VARCHAR2(25), 
 phone_number VARCHAR2(20),  hire_date DATE, salary NUMBER(8,2) , 
 department_id NUMBER(4)이다.
```

```sql
CREATE TABLE employees_demo
 ( employee_id NUMBER(6) ,
   last_name VARCHAR2(25),
   phone_number VARCHAR2(20) ,
   hire_date DATE, salary NUMBER(8,2) ,
   department_id NUMBER(4) )
```

# 5. 다음의 조건에 맞게 뷰(View)를 생성하는 명령문을 작성하시오.(7점)
  뷰 이름:clerk 
  조건: employees 테이블에서 job_id가 'PU_CLERK' 이거나 'SH_CLERK'인 자료 중 컬럼이 employee_id, last_name, department_id, job_id를 select하여 만든다.

```sql
CREATE VIEW clerk AS
 SELECT employee_id, last_name, department_id, job_id
 FROM employees WHERE job_id IN ( 'PU_CLERK' ,'SH_CLERK' , job_id = 'ST_CLERK');
```


