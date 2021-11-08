## Part6. Advanced Operators

### 1. Operator Methods ***

기존 연산자가 새로운 형식을 지원하도록 확장 하는 방법에 대해 공부합니다.

#### 1) 연산자 메소드 문법

```swift
// Syntax
static func operator(parameters) -> ReturnType {
	statements
}
```

#### 2) == 연산자 구현

```swift
struct Point{
	var x = 0.0
	var y = 0.0
}

extension Point: Equatable {
    static func ==(lhs: Point, rhs: Point) -> {
        return (lhs.x == rhs.x) && (lhs.y == rhs.y)
    }
}

let p1 = Point(x: 12, y: 34)
let p2 = Point(x: 67, y: 39)

p1 == p2	//false
p1 != p2	//true
```

1. 연산자 메소드는 Point 구조체에서 직접 구현해도 되지만 보통 extension으로 구현
2. Swift에서 비교 기능을 구현할때는 equatable 프로토콜을 채용하고, 거기에 선언되어 있는 메소드를 연산자 메소드로 구현한다.
3. Equatable 안의 함수를 지워도 에러 안남. Point 구조체를 보면 Double 형식의 변수를 사용하는데, Double은 equalTo 연산자로 비교 가능. 다시 말해 equatable protocol을 채용하고 있다. 지금처럼 형식에 Equatalbe 프로토콜을 채용한 저장속성만 선언되어 있다면, 컴파일러가 자동으로 구현을 추가한다.

#### 3) \- 연산자 구현

``` swift
extention Point {
    static prefix func -(pt: Point) -> Point {
        return Point(x: -pt.x, y: -pt.y)
    }
}

let p3 = -p1
p3.x	// -12
p3.y	// -34
```

#### 4) ++ 연산자 구현

```swift
extension Point {
	// 연산 도중에 현재 값을 바꿔야 하기 때문에 입출력 파라미터로 선언한다 (inout)
    static postfix func ++(pt: inout Point) -> Point {
        let ret = pt
        pt.x += 1
        pt.y += 1
        return ret
    }
}

var p4 = Point(x: 1.0, y: 2.0)
let p5 = p4++
p5.x	//1
p5.y	//2
p4.x	//2
p4.y	//3
```



 

### 2. Int 형식에 저장된 값과 Double 형식에 저장된 값 더하기 (실습)

```swift
import Foundation


let a = 1
let b = 2.3

var validCount = 0

extension Double {
    static func +(a:Int, b:Double)  -> Double {
        return Double(a) + b
    }
    static func +(a:Double, b:Int) -> Double {
        return b + a	// +(a:Int, b:Double) 가 이미 선언되어 있어서        
    }
}

if a + b == 3.3 {
   validCount += 1
}

if b + a == 3.3 {
   validCount += 1
}

print(validCount)
```



### 3. Custom Operators ***

Swift가 제공하지 않는 새로운 연산자를 직접 구현하는 방법에 대해 공부합니다.

- 연산자 선언 문법

  ```swift
  prefix operator 연산자
  postfix operator 연산자
  infix operator 연산자
  
  static prefix func 연산자(파라미터) -> 리턴형 {
  	// 실행할 코드
  }
  
  static postfix func 연산자(파라미터) -> 리턴형 {
  	// 실행할 코드
  }
  
  static func 연산자(파라미터) -> 리턴형 {
  	// 실행할 코드
  }
  ```

  - Reserved Tokens
    (, ), {, }, [, ], ., ,, :, ;, =, @, #, & (prefix operator), ->, , ?,
    ! (postfix operator)

  - First Character
    /, =, -, +, !, *, %, <, >, &, |, ^. ?, ~

  - 연산자를 가능한 단순한 형태로 선언하기.

  - 기존에 있는 연산자와 함께 사용했을 때, 모호함이 없도록 선언해야 한다.

    ![image-20211109004744037](C:\Users\Kim Hyo Rim\AppData\Roaming\Typora\typora-user-images\image-20211109004744037.png)

    ![image-20211109004923352](C:\Users\Kim Hyo Rim\AppData\Roaming\Typora\typora-user-images\image-20211109004923352.png)

  - ```
    1 *+* 2 + 3 // Adjacent operators are in unordered precedence groups
    			// 연산자 우선순위 미지정
    ```

    ![image-20211109005240744](C:\Users\Kim Hyo Rim\AppData\Roaming\Typora\typora-user-images\image-20211109005240744.png)

- 우선순위 그룹

  <img src="C:\Users\Kim Hyo Rim\AppData\Roaming\Typora\typora-user-images\image-20211109005313816.png" alt="image-20211109005313816" style="zoom: 67%;" />

  ![image-20211109005614969](C:\Users\Kim Hyo Rim\AppData\Roaming\Typora\typora-user-images\image-20211109005614969.png)





### 4. 2의 거듭 제곱을 계산하는 ** 연산자 구현하기 (실습)	

- 새로운 ** 연산자를 선언하고 2의 거듭 제곱을 계산하도록 구현해 주세요.
- "*" 연산자와 동일한 그룹에 속해야 합니다.

```swift
import Foundation

infix operator **: MultiplicationPrecedence

extension Int {
    static func **(left: Int, right: Int) -> Int {
        var ret = 1
        for num in 1 ... right {
            ret *= left
        }
        return ret
    }
}

var validCount = 0

if 2 ** 3 == 8 {
   validCount += 1
}

if 2 ** 10 == 1024 {
   validCount += 1
}

print(validCount)
```

