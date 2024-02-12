# 1.나이 계산
```
나이를 세는 방법은 여러 가지가 있습니다.
그중 한국식 나이는 태어난 순간 1살이 되며 해가 바뀔 때마다 1살씩 더 먹게 됩니다.
연 나이는 태어난 순간 0살이며 해가 바뀔 때마다 1살씩 더 먹게 됩니다.
각각 나이의 계산법은 다음과 같습니다.

한국식 나이 : 현재 연도 - 출생 연도 + 1
연 나이 : 현재 연도 - 출생 연도

출생 연도를 나타내는 정수 year와 구하려는 나이의 종류를 나타내는 문자열 age_type이 주어질 때 2030년에 몇 살인지 출력하도록 빈칸을 채워 코드를 완성해 주세요.
age_type이 "Korea"라면 한국식 나이를, "Year"라면 연 나이를 출력합니다.

<<조건>>
1950 ≤ year ≤ 2030
age_type은 "Korea" 또는 "Year"만 주어집니다.
```
```java
import java.util.Scanner;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int year = sc.nextInt();
        String age_type = sc.next();
        int answer = 0;

        if (age_type.equals(1)) {
            answer = (2);
        }
        else if (age_type.equals("Year")) {
                    (3);
        }
        System.out.println(answer);
    }
}
```

### 정답
```
(1) : "korea"
(2) : 2030 - year + 1
(3) : answer = 2030 - year
```

# 2. 저축하기
```
진우는 돈을 모으기 위해 저축을 하려고 합니다.
목표로 하는 금액은 100만 원이며, 첫 달에 일정 금액을 넣은 뒤 70만 원까지는 매월 조금씩 저축하다가 70만 원 이후부터는 월 저축량을 늘려 빠르게 목표 금액을 달성하고자 합니다.

첫 달에 저축하는 금액을 나타내는 정수 start,
두 번째 달 부터 70만 원 이상 모일 때까지 매월 저축하는 금액을 나타내는 정수 before,
100만 원 이상 모일 때 까지 매월 저축하는 금액을 나타내는 정수 after가 주어질 때,
100만 원 이상을 모을 때까지 걸리는 개월 수를 출력하도록 빈칸을 채워 코드를 완성해 주세요.
```

```java
import java.util.Scanner;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int start = sc.nextInt();
        int before = sc.nextInt();
        int after = sc.nextInt();

        int money = start;
        int month = 1;
        while (money < 70) {
            money += (1);
            month++;
        }
        while ( (2) < 100) {
            (3);
            month++;
        }
        System.out.println(month);
    }
}
```

### 정답
```
(1) : before
(2) : money
(3) : money += after;
```

# 3. 홀짝 구분하기
```
자연수 n이 입력으로 주어졌을 때 만약 n이 짝수이면 "n is even"을, 홀수이면 "n is odd"를 출력하는 코드를 작성해 보세요.
```

### 코드
```java
import java.util.Scanner;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();

         /////////////////////////////////
        코드 작성하기
        /////////////////////////////////
       
    }
}
```

### 정답
```java
import java.util.Scanner;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        
        if( n % 2 != 0){
            System.out.println(n+" is odd");
        } else {
            System.out.println(n +" is even");
        }
    }
}
```

# 4. 문자열 돌리기
```
문자열 str이 주어집니다.
문자열을 시계방향으로 90도 돌려서 아래 입출력 예와 같이 출력하는 코드를 작성해 보세요.

<<입출력 예>>
입력
abcde

출력
a
b
c
d
e
```

### 코드
```java
import java.util.Scanner;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String a = sc.next();
        /////////////////////////////////
        코드 작성하기
        /////////////////////////////////
    }
}
```

### 정답
```java
import java.util.Scanner;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String a = sc.next();
        
        for(int i = 0; i < a.length(); i++){
            System.out.println(a.charAt(i));
        }
    }
}
```

# 5. 문자 리스트를 문자열로 변환하기
```
문자들이 담겨있는 배열 arr가 주어집니다.
arr의 원소들을 순서대로 이어 붙인 문자열을 return 하는 solution함수를 작성해 주세요.
```

### 제한사항
- 1 ≤ arr의 길이 ≤ 200
    - arr의 원소는 전부 알파벳 소문자로 이루어진 길이가 1인 문자열입니다.

```
입출력 예
arr	            result
["a","b","c"]	"abc"
```

### 코드
```java
class Solution {
    public String solution(String[] arr) {
        String answer = "";
         /////////////////////////////////
        코드 작성하기
        /////////////////////////////////
        return answer;
    }
}
```

### 정답
```java
class Solution {
    public String solution(String[] arr) {
        String answer = "";
        
        for(int i = 0; i < arr.length; i++){
            answer += arr[i];
        } 
        return answer;
    }
}
```
