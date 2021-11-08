## Part5. Operators

### 1. Operator Basics

연산자 기초 이론을 공부합니다.

- 연산자(operator)외 피연산자(operand)
- 연산자의 종류
  - Unary, Binary, Ternary Operator
  - Prefix, Postfix, Infix Operator
- 연산자 우선순위
- 연산자 결합규칙
  - Left Associative
  - Right Associative 



### 2. Arithmetic Operators

사칙연산과 나머지 연산에 사용하는 산술 연산자에 대해 공부합니다.

- \+ 연산자

- \- 연산자

- \* 연산자

- / 연산자

- % 연산자 : 실수연산에서는  메소드 활용 `c.truncatingRemainder(dividingBy: d)`

  

### 3. 올바를 산술 연산자 채우기(실습)



### 4. Overflow Operators

값 오버플로우가 무엇인지, 그리고 오버플로우 연산자를 사용해서 오버플로우를 허용할 때 값이 어떻게 변경되는지에 대해 공부합니다.

- 오버플로우
- &+ 연산자 : C 언어와 같이 (자료형).max &+ 1 = (자료형).min
- &- 연산자
- &* 연산자



### 5. 올바른 오버플로우 연산자 채우기(실습)



### 6. Comparison Operators

값이 동일성과 크기를 비교하는 방법에 대해 공부합니다. 

- 피연산자의 자료형 일치시켜야함

- == 연산자 (equal to)
- != 연산자 (not equal to)
- < 연산자 (greater than)
- <= 연산자 (greater than or equal to)
- \> 연산자 (less than)
- \>= 연산자 (less than or equal to)



### 7. 올바른 비교 연산자 채우기(실습)



### 8. Logical Operators

- ! 연산자
- && 연산자
- || 연산자



### 9. 올바른 논리 연산자 (실습)



### 10. Ternary Conditional Operator

- 삼항연산자

- 주로 2개의 값 중 하나를 선택해야 할 때 사용

- `condition ? expr1[True] : expr2[False]`

- ```swift
  hour < 11 ? "Good Morning" : 
  	(hour < 17 ? "Good Afternoon" : "Good Evening")
  // 위와 같이 삼항연산자를 중복해서 쓰는것 보다는 if문을 쓰는게 더 직관적
  ```



### 11. 조건 연산자로 짝수 or 홀수 출력하기(실습)



### 12. Short-circuit Evaluation, Side Effect

논리 연산자가 논리식을 평가하는 방법에 대해 공부합니다.

- **단락 평가**

  ```swift
  var a = 1
  var b = 1
  
  func updateLeft() -> Bool {
  	a += 1
  	return true
  }
  
  func updateRight() -> Bool {
  	b += 1
  	return true
  }
  
  if updateLeft() || updateRight {
      // updateLeft()만 실행되어도 True이므로
      // updateRight()는 실행 되지 않음
  }
  
  print(a)		//2
  print(b)		//1
  ```

- **Side Effect**

  - 개념 : 코드의 실행 결과로 인해서 값 또는 상태가 변경되는것
  - 위의 예제에서 한 번의 side effect가 발생(a)
  - side effect를 고려하여 코딩하기 (논리식에서의 사용은 피하기)



### 13. Bitwise Operators

- Not Operator `~`

- And Operator `&`

- Or Operator `|`

- XOR Operator `^`

- Left Shift `<< `  : *2 와 동일 

  - 오른쪽 새로운 칸은 0으로 채움

- Right Shift `>>` : /2 와 동일 

  - Unsigned는 왼쪽 새로운 칸은 0으로 채움

  - Signed의 경우 기존의 부호비트를 그대로 사용

    

### 14. Assignment Operators

값을 저장하는데 사용하는 할당 연산자와 복합 할당 연산자에 대해 공부합니다.

##### 1) Assignment Operators

- = 연산자
- lvalue와 rvalue (등호가 기준)
  - lvalue는 메모리 공간을 의미
  - rvalue는 저장할 값을 의미(변수도 가능)

##### 2) Compound Assignment Operators

- += 연산자
- -= 연산자
- *= 연산자
- /= 연산자
- %= 연산자
- &= 연산자
- |= 연산자
- = 연산자
- <<= 연산자
- \>>= 연산자



### 15. Range Operators

범위 연산자를 통해서 범위를 표현하는 방법에 대해 공부합니다.

##### 1. Closed Range Operator

​	`a ... b`, `a ...`, ` ... a`

- a 이상 b 이하
- a가 b보다 작아야함 (Can't form Range with upperBound < lowerBound)
- (1 ... 10 ).reversed()
- 정수, 실수, 문자열 모두 사용 가능

``` swift
let list = ["A", "B", "C", "D", "E"]
list[2...]	// ["C", "D", "E"]
list[...2]	// ["A", "B", "C"]

for (num in 1 ... 10) {
    // doSomething
}
```



##### 2. Half-Open Range Operator

 	`	a ..< b` , `..< a`

- a 이상 b 미만, a 미만



##### 3. One-Sided Range

​	`a ...`, 



##### 4. 자주 사용하는 메소드

```swift
let range = ... 5
range.contains(7)		// false
range.contains(1)		// true 
range.contains(-1)		// true
```





### 16. 올바른 범위 연산자 채우기(실습)
