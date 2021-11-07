## Part4. Literals, Data Types

### 1. Data Tyeps with Memory

자료형에 대한 개요를 설명하고, 자료형을 이해하는데 필요한 메모리 저장 방식에 대해 공부합니다.

- **자료형의 구분** 

  - Built-in Data Type : integer, float, boolean, character, string
  - Custom Data Type

- **메모리 구조와 크기**

  - 메모리 : 0과 1을 저장할 수 있는 저장 공간
  - bit < byte (8 bit) <  ... < Yotta

- **데이터 저장 방식**

  - 정수 저장

    <img src="https://user-images.githubusercontent.com/59546818/140657240-7d948b35-c95f-47aa-87bb-f321f825f96f.png" alt="image-20211108023835852" style="zoom:50%;" />
    
  - 실수 저장(정수에 비해 더 큰 범위 저장 가능)

    <img src="https://user-images.githubusercontent.com/59546818/140657333-76a993de-820a-44a1-8143-876d3ce8c192.png" alt="image-20211108023835852" style="zoom:50%;" />

- **CPU와 메모리의 관계**

  - 주소 Register를 사용하여 CPU가 메모리에 접근

- **Overflow**

  - 메모리에 저장할 수 있는 값을 초과한 경우(swift에서는 error로 판단)



### 2. Numbers

Swift에서 숫자를 표현하는 방법과 숫자를 저장하는 자료형에 대해 공부합니다.

- 숫자 리터럴

  ```swift
  0.23
  1.23e4	//10진수 지수
  0xAp2	//16진수 지수
  1_000_000	// , 대신 사용
  
  10		//10진수
  0b1010  //2진수
  0o12	// 8진수
  0xA		// 16진수
  ```

- 정수 자료형과 실수 자료형

  실수 default는 double (float 는 manually 지정)

  ```swift
  Int8.min
  Int8.max 
  MemoryLayout<Int8>.size
  
  
  ```

- Signed와 Unsigned

  ```swift
  // Signed : Int8, Int16, Int32, Int64
  // Unsigned : UInt8, UInt16, UInt32, UInt64
  
  let num = 123
  type(of: num)
  ```

- 저장 가능한 값의 범위

  

### 3. 숫자 리터럴과 숫자 자료형 이해하기(실습)



### 4. Boolean

- 불린 리터럴 (0과 1을 대신 사용 불가능 )

- 불린 자료형

  ```swift
  let isValid : Bool = true
  
  let str = " "
  str.isEmpyt
  
  if isValid {
      ...
  }
  
  while !isValid {
      
  }
  ```



### 5. 불린 자료형 이해하기(실습)

`=` 양 옆으로 whitespace가 있어야 error 안남



### 6. Strings and Characters

문자열과 문자를 표현하고 저장하는 방법에 대해 공부합니다.

- 문자열 리터럴

- 문자열 자료형

- 문자 자료형 `let ch: Character = "1"`

  

### 7. 문자열, 문자 자료형 이해하기(실습)



### 8. Type Interface

형식 추론을 통해 자료형을 생략할 때 추론의 단서가 무엇인지 공부합니다.

- 형식 추론(Type Inference)

- Type Annotation

  ```swift
  // 정수, 실수, char type을 지정할 때 사용
  // compile 시간을 단축 
  
  let name : Type = value
  let value :Double
  value = 12.3
  ```

  

### 9. Type Annotation 이해하기(실습)



### 10. Type Satefy

Swift가 안전한 언어인 이유를 형식 안정성을 통해 설명합니다. 

```swift
let a = 7
// let b : Int8 = a 	// error(Cannot convert value of type 'Int'to specified...)
// let c : Int64 = a	// 같은 메모리 크기임에도 불구하고 error

// let a : Int = 1.24  	// error 특정 언어에서는 아래의 코드를
						// 에러없이 1로 변환하여 실행하는 경우도 있음

let rate = 1.94
let amt = 10_000_000
let result = rate * Double(amt) // Type Conversion
```





### 11. Type Conversion

서로 다른 형식의 값을 원하는 형식으로 변환하는 방법에 대해 공부합니다.

- Type Conversion : 메모리에 저장된 값을 다른 형식으로 바꿔서 새로운 값을 생성함

- Type Casting : 메모리에 저장된 값을 그대로 두고 컴파일러가 다른 형식으로 처리하도록 지시

- Syntax : `Type(value)`

  ```swift
  let a = 123
  let b = 4.56
  
  Double(a) + b	// 123.0 + 4.56
  a + Int(b)		// 123 + 4
  
  let c = Int8(a)
  let d = Int.max
  // let e = Int8(d)	//Fatal Error
  
  let str = "123"
  let num = Int(str)
  
  let str2 = "Hi"
  let num = Int(str)		//type nil
  
  ```

  

### 12. 자료형이 다른 두 값을 더하기(실습)



### 13. Type Alias

자료형에 새로운 이름을 추가하는 방법에 대해 공부합니다.

- Syntax : `typealias NewName = TypeName`

  ```swift
  typealias Coordinate = Double	// 좌표값
  
  let lat: Coordinate = 12.34		// latitude
  let lon: Coordinate = 56.78		// longitude
  ```

  

