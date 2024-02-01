# 1. DCL에 대해서 정의하시오
### 정답
```
데이터베이스에 접근하고 객체들을 사용하도록 권한을 주고 회수하는 명령어
```

# 2. 다음 조건을 만족하는 테이블 스페이스를 생성하는 쿼리문을 작성하시오. (10점)
    1) 테이블 스페이스 이름 : user_exam

    2) 데이터 파일 이름 : C:/Exam/user_exam.dbf

    3) 용량 : 10MB

### 정답
```sql
CREATE TABLESPACE user_exam DATAFILE 'C:/Exam/user_exam.dbf' SIZE 10M;
```

# 3. 생성된 계정의 이름을 검색하기 위한 쿼리문을 작성하시오. (10점)
### 정답
```sql
SELECT USERNAME FROM DBA_USERS;
```

# 4. 다음 조건을 만족하는 쿼리문을 작성하세요. (10점)
- 계정을 생성하는쿼리문 작성하기

```SQL
(1) baby identified by baby;
```
### 정답
```SQL
CREATE USER
```

# 5. 생성된 테이블 스페이스를 확인하기 위해서 테이블 스페이스의 목록을 조회할 수 있는 쿼리문을 작성하시오. (10점)
### 정답
```sql
SELECT * FROM dba_tablespaces;
SELECT * FROM user_tablespaces;
```

# 6. 다음 조건을 만족하는 사용자를 생성하는 명령어를 작성하시오.(10점)
- 사용자 ID : joe
-  비밀번호 : black
-  기본 tablespace : hr_data01
-  temporary tablespace : temp

### 정답
```sql
create user joe identified by black default tablespace hr_data01 temporary tablespace temp;
```

# 7. 릴레이션, 속성, 튜플에 대해서 설명하시오. (10점)
### 정답
```
릴레이션 (Relation) : 데이터를 표의 형태로 표현한 것입니다.
속성 (Attribute; 애트리뷰트) : 데이터베이스를 구성하는 가장 작은 논리적 단위입니다. (Column; 열 (혹은 필드; Field 라고도 함))
튜플 (Tuple) : 릴레이션을 구성하는 각각의 행을 뜻합니다. 
```

# 8. 다음의 제시한 내용을 보고 테이블을 만드는 명령문을 작성하시오.(10점)

```
 테이블 이름:employees_demo
 각 속성이름 및 데이터형 : employee_id NUMBER(6),
                           last_name VARCHAR2(25), 
                           phone_number VARCHAR2(20),
                           hire_date DATE, salary NUMBER(8,2), 
                           department_id NUMBER(4)이다.
```
### 정답
```sql
CREATE TABLE employees_demo
 ( employee_id NUMBER(6) ,
   last_name VARCHAR2(25),
   phone_number VARCHAR2(20) ,
   hire_date DATE, salary NUMBER(8,2),
   department_id NUMBER(4) )
```

# 9. 뷰(View)의 정의를 작성하시오(10점)

### 정답
```
사용자에게 접근이 허용된 자료만을 제한적으로 보여주기 위해 하나 이상의 기본 테이블로부터 유도된, 이름을 가지는 가상 테이블(Virtual Table)이다.
```

# 10. 다음의 조건에 맞게 뷰(View)를 생성하는 명령문을 작성하시오.(10점)
- 뷰 이름:clerk 
- 조건: employees 테이블에서 job_id가 'PU_CLERK' 이거나 'SH_CLERK'인 자료 중 컬럼이 employee_id, last_name, department_id, job_id를 select하여 만든다.

```sql
CREATE VIEW clerk AS
 SELECT employee_id, last_name, department_id, job_id
 FROM employees WHERE job_id IN ( 'PU_CLERK' ,'SH_CLERK');
```



