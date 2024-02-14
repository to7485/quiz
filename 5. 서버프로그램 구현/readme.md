# 1. 다음 지시사항에 따라 회원관리 서버프로그램을 구현하시오.
- 프로젝트명 : ServerProgram1
- 통합개발환경 : eclipse
- WAS : tomcat

### 답안제출방식
- 프로젝트를 추가한 eclipse화면을 캡쳐하여 제출하시오.


### 정답
![image](image/1-1.png)

## 2. 웹페이지에서 사용할 공통 모듈들을 구현하시오

- 테이블 생성및 SQL문은 아래와 같이 제공됩니다.
```sql
-- 시퀀스 생성하기
CREATE SEQUENCE MEMBER_SEQ;

CREATE TABLE MEMBER_TABLE(
	NO NUMBER,
	ID VARCHAR2(50),
	NAME VARCHAR2(50),
	GRADE VARCHAR2(50),
	POINT NUMBER
);

-- selectAll
SELECT NO, ID, NAME, GRADE, POINT FROM MEMBER_TABLE;

-- login
SELECT NO, ID, NAME, GRADE, POINT FROM MEMBER_TABLE WHERE ID= ? AND NAME=?;

-- deleteMember
DELETE FROM MEMBER_TABLE WHERE NO=?;

-- updateMember
UPDATE MEMBER_TABLE SET NAME= ?, POINT = ? GRADE = ? WHERE NO = ?;

-- updatePoint
UPDATE MEMBER_TABLE SET POINT = POINT + 10;
```

1. MEMBER_TABLE 테이블의 정보를 전달할 때 사용하는 MemberDTO클래스를 구현하시오.

### 정답

```java
/***** MemberDTO.java *****/
package dto;

public class MemberDTO{


}public class MemberDTO {
    private int no;
    private String id;
    private String name;
    private String grade;
    private int point;

    // Getter 및 Setter 메서드
    public int getNo() {
        return no;
    }

    public void setNo(int no) {
        this.no = no;
    }

    public String getId() {
        return id;
    }

    public void setId(String id) {
        this.id = id;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getGrade() {
        return grade;
    }

    public void setGrade(String grade) {
        this.grade = grade;
    }

    public int getPoint() {
        return point;
    }

    public void setPoint(int point) {
        this.point = point;
    }
}
```

2. DB설정을 저장하는 DBConfig 인터페이스와 DB접속과 해제를 담당하는 DBConnector 클래스를 구현하시오.
##### DBConnector 클래스는 싱글톤으로 구현하시오

(1) jdbc 드라이버 : oracle.jdbc.driver.OracleDriver

(2) URL : jdbc:oracle:thin:@127.0.0.1:1521:xe

(3) USER : SERVER_USER

(4) PASSWORD : 1111


3. DB 처리를 담당하는 MemberDAO 클래스를 싱글톤으로 구현하시오

4. 응답View와 이동방식(redirect, forward)을 저장할 때 사용하는 ModelAndView클래스를 구현하시오




