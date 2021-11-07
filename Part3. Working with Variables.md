## Part3. Working with Variables

### 1.  Variables and Constans

##### 1) Variables  : var

```swift
// Syntax
//var variableName = initialValue

var name = "Swift" 
var year = 2018
var valid = false
var x = 0.0, y = 0.0, z = 0.0
print(name)

// year = "2019" 		// String값으로 재할당 불가
```

##### 2) Constants : let

Swift에서는 상수를 더욱 선호, 추후 변경해야 한다면 var 키워드로 변경

```swift
let name = "Yoona"
// name = "Steve" 		// cannot assign to value
```



### 2. 변수와 상수 올바르게 선언하기(실습)



### 3. 자료형 직접 선언하기(실습)



### 4. Naming Convention

Swift의 이름 정의 규칙인 Camel Case에 대해 공부합니다.

- UpperCamelCase : Class, Structure, Enumeration, Extension, Protocol
- lowerCamelCase : Varibale, Constant, Function, Property, Parameter 



### 5. Scope

전역범위와 지역범위, 그리고 선언된 위치에 따라서 접근 가능성이 어떻게 달라지는가에 대해서 공부합니다.

##### 1) Global Scope

##### 2) Local Scope : {} 안

```swift
let g1 = 123

func doSome() {
    let g1 = 987
    print(gl) // 987
}

struct Scope {
    // 선언이 와야 하는 위치(속성이나 메소드)
    // g1 호출 불가, if문같은 statement도 불가 
    func doSomethin () {
        g1 = 456 // 메소드의 로컬 scope이기 때문에 g1 호출 가능
    }
}
```

