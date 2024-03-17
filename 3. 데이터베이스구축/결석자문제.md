# 1. 테이블 스페이스를 생성하시오
- 테이블 스페이스를 생성하는데 용량은 500MB로 성정하고 자동확장 기능(무한)을 사용한다.
- 테이블 스페이스 명은 custom_space 데이터 파일명은 c:custom_space.dbf 로 지정한다.

### 정답
```SQL
--1. 테이블 스페이스 생성
CREATE TABLESPACE custom_space
DATAFILE 'c:\custom_space.dbf' SIZE 500M
AUTOEXTEND ON NEXT 100M
MAXSIZE UNLIMITED;
```

# 2. 사용자를 생성하고 권한을 주시오.
- 사용자 생성을 하나 하여(계정명 NAM2626) 접속 권한과 DDL 권한, 뷰 생성 권한만 주시오.
- 테이블 스페이스는 1번에서 만든걸로 지정하시오.

### 정답
```SQL
--2. 사용자 생성 및 권한 부여, 테이블 스페이스 지정
CREATE USER NAM2626 IDENTIFIED BY 123456
DEFAULT TABLESPACE USER_TABLE;
GRANT CONNECT, RESOURCE, CREATE VIEW TO NAM2626;
```

# 3. 오라클 설치 완료 보고서를 쓰기 위해 생성한 사용자 계정의 권한 정보를 확인하시오.
### 정답
```SQL
--3. 사용자 계정 권한 정보 조회
SELECT * FROM DBA_ROLE_PRIVS WHERE GRANTEE = 'NAM2626';
```
# 4. 다음의 제시한 내용을 보고 테이블을 만드는 명령문을 작성하시오.(20점)
### 정답
```SQL
테이블 이름:employees_demo
각 속성이름 및 데이터형 : employee_id NUMBER(6),
                          last_name VARCHAR2(25), 
                          phone_number VARCHAR2(20),
                          hire_date DATE, salary NUMBER(8,2), 
                          department_id NUMBER(4)이다.

CREATE TABLE employees_demo
 ( employee_id NUMBER(6) ,
   last_name VARCHAR2(25),
   phone_number VARCHAR2(20) ,
   hire_date DATE, salary NUMBER(8,2),
   department_id NUMBER(4) )

 ```

 

# 5. 다음의 조건에 맞게 뷰(View)를 생성하는 명령문을 작성하시오.(20점)

- 뷰 이름:clerk 
- 조건: employees 테이블에서 job_id가 'PU_CLERK' 이거나 'SH_CLERK'인 자료 중 컬럼이 employee_id, last_name, department_id, job_id를 select하여 만든다.

### 정답
```SQL
CREATE VIEW clerk AS
 SELECT employee_id, last_name, department_id, job_id
 FROM employees WHERE job_id IN ( 'PU_CLERK' ,'SH_CLERK');

또는

CREATE VIEW clerk AS
(
    SELECT employee_id, last_name, department_id, job_id
    FROM employees
    WHERE job_id IN ('PU_CLERK', 'SH_CLERK')
);
```












