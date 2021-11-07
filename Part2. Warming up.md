## Part2. Warming up

### 1.  Token, Expression, Statement

##### 1) Token 

개념 : 공백이나 점으로 분리할 수 없는 가장 기본적인 요소(가장 작은 단위의 요소)

종류 : Identifiers, Keywords, Puctuations, Operators, Literals

ex) `2 + 3;` 에서 토큰은 4개이다 

##### 2) Expressions

- 개념 : 하나 이상의 토큰이 모여서 하나 이상의 값을 도출하는 식

- Evaluate : 코드를 실행해서 값을 얻는다

- Arithmatic Expressions

- Boolean Expressions

```swift
let x = 7
x+1 // 8
x < 10
```

##### 3) Statement

- 개념 : 표현식이 하나 이상 모여서 특정 작업을 실행하는 코드

- 세미콜론 생략가능

- 종류 : if, switch, guard, for-in, while



### 2. Literal, Identifier, Keyword

##### 1) Literal

- 개념 : 코드내에서 의미가 변하지 않고 있는 그대로 사용되는 값
- `let x = 7` 에서 7, `let x = 5 + 7` 에서 5와 7
- Integer Literlas, Floating-point Literals, String Literals, Boolean Literals, ***nil Literals***



##### 2) Identifier

- 개념 : 식별자는 코드에 포함된 요소를 구별하는데 사용하는 요소 
- `let x = 7` 에서 x



##### 3) Keywords

- 개념 : 프로그래밍 언어가 제공하는 기능을 위하여 예약되어 있는 단어
- `let x = 7` 에서 let
- associatedtype, class, deinit, enum, extension, fileprivate, func, import, init 등

- 키워드는 식별자 이름으로 사용불가



### 3. Compile, Link, Run

##### 1) Compile

- source code -> binary code (Warning, Error)

##### 2) Link

- Framework나 Library에 포함된 코드가 연결

##### 3) Run

- build : compile + link + 실행파일 생성 + 부가적인 과정

- 실행파일 생성 방법 1: Debug Mode (실행파일에 디버그 정보 포함)

- 실행파일 생성 방법 2: Release Mode (실행파일에 디버그 정보 미포함 + 최적화)

- Compile Time : compile과 link가 완료되어 실행파일이 생성되는 시점까지

- Runtime : 생성된 파일을 시뮬레이터나 실제 디바이스에서 실행하는 시점




### 4. Special Characters

  1) `!`  Exclamation Mark : 논리 부정
  2) `~`  Tilde : bit연산자
  3) `\` Back Tick : 키워드를 identifier로 바꿈
  4) `@` At Sybol : 코드 자체의 특성 지정
  5) `#` Sharp / Pound / Hashtag : Swift가 제공하는 특별한 명령어들이 #으로 시작
  6) `$` Dollar Sign : 클로저에서 파라미터 이름을 대체할 떄 사용 

7. `%` Percent Sign : 나머지 연산
8. `^` Carot : 비트연산
9. `&` Ampersand : 주로 메모리 주소를 얻거나 참조를 전달할 때 사용
10. `*` Asterisk : 곱하기 연산
11. `( )` Parentheses : 함수 호출, 계산 순서 지정
12. `-`Minus Sign / Hyphen
13. `_` Underscore : 와일드 카드 패턴에서 자주 사용

14. `=` 저장, `==` 비교
15. `+` plus sign : 덧셈
16. **`[ ]` Square Bracket : 컬렉션에 저장된 값에 접근시 사용 -> 서브스크립트문법**
17. **`{ }` Brace : 코드 블럭의 범위 지정**
18. `\` Backslash : String 인터폴레이션 문법 / key Path 표현
19. `|` Vertical Bar / Pipe : 논리연산, 비트연산
20. `;` Semicolon
21. `:` Colon : 자료형 선언, Dict에서 key, value 구분
22. `,` Comma : 나열
23. `.` Period : 메소드 호출 / 속성 접근
24. **` < >` Angle Bracket : 크기 비교, Generic의 형식 파라미터 지정**
25. `/` Slash : 경로 지정
26. `?` Question Mark : Optional

### 5. First Class Citizen

- can be stored in variables and data structures
- can be passed as a parameter to a function
- can be returned as the result of a function

