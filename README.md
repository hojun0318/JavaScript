# 식별자 정의와 특징
```
카멜 케이스 (camelCase, lower-camel-case)
    - 변수, 객체, 함수에 사용

파스칼 케이스(PascalCase, upper-camel-case)
    - 클래스, 생성자에 사용

대문자 스네이크 케이스(SNAKE_CASE
    - 상수 (constants)에 사용
    - 상수 : 개발자의 의도와 상관없이 변경될 가능성이 없는 값을 의미
```

# 변수 선언 키워드
- Python과 다르게 JavaScrips는 변수를 선언하는 키워드가 정해져 있음
1. let
    - 블록 스코프 지역 변수를 선언 (추가로 동시에 값을 초기화)
2. const
    - 블록 스코프 읽기 전용 상수를 선언 (추가로 동시에 값을 초기화)
3. var
    - 변수를 선언 (추가로 동시에 값을 초기화)

### [참고] 선언, 할당, 초기화
- 선언 (Declaration)
    - 변수를 생성하는 행위 또는 시점
```
let foo
console.log(foo)
```
- 할당 (Assignment)
    - 선언된 변수에 값을 지정하는 행위 또는 시점
```
foo = 11
console.log(foo)
```
- 초기화 (Initialization)
    - 선언된 변수에 처음으로 값을 저장하는 행위 또는 시점
```
let bar = 0
console.log(bar)
```

### [참고] 블록 스코프 (block scope)
- if, for 함수 등의 중활호 ({})내부를 가리침
- 블록 스코프를 가지는 변수는 불록 바깥에서 접근 불가능

# 변수 선언 키워드
## let
- 재할당 가능 & 재선언 불가능
```
let number = 10     // 1. 선언 및 초기화 할당
number = 20         // 2. 재할당
```
```
let number = 10     // 1. 선언 및 초기과 할당
lel number 2- 20    // 재선언 불가
```
- 블록 스코프를는 지역 분수를 선언, 선언과 동시에 원하는 값으로 초기화 할 ㅅ 있음

## const
- 재할당 불가능 & 재선언 불가능
```
const mumber= 10    // 1. 선언 및 초기값 할당
number = 10         // 2. 재할당 불가능
```
```
const number = 10   // 1. 선언 및 초기값 할당
const number = 20   // 2. 재선언 불가능
```
- 선언 시 반드시 초기값을 설정해야 하며, 이후 값 변경이 불가능
- let과 동일하게 블록 스코프를 가짐


## var
- 재할당 가능 & 재선언 가능
- ES6 이전에 변수를 선언할 때 사용되던 키워드
- "호이스팅" 되는 특성으로 인해 예기치 못한 문제 발생 가능
    - 따라서 ES6 이후부터는 var 대신 const와 let을 사용하는 것을 권장
- 함수 스코프(function scope)를 가짐

**변수 선언 시 var, const, let 키워드 중 하나를 사용하지 않으면 자동으로 var로 선언**

### [참고] 함수 스코프 (function scope)
- 함수의 중괄호 내부를 가리킴
- 함수 스코프를 가지는 변수는 함수 바깥에서 접근 불가능

### [참고] 호이스팅 (hoisting)
- 변수를 선언 이전에 참조할 수 있는 현상
- var로 선언된 변수는 선언 이전에 참조할 수 있으며, 이러한 현상을 호이스팅이라고 함
- 변수 선언 이전의 위치에서 접근 시 undefined를 반환
- 즉, JavaScript에서 변수들은 실제 실행시에 코드의 최상단으로 끌어 올려지게 되며 (hoisted) 이러한 이유 때문에 var로 선언된 변수는 선언 시에 undefined로 값이 초기화되는 과정이 동시에 일어남
- 반면 let, const는 호이스팅이 일어나면 에러를 발생시킴
- 변수를 선언하기 전에 접근이 가능한 것은 코드의 논리적인 흐름을 깨뜨리는 행위이며 이러한 것을 방지하기 위해 let, const가 추가되었음
    - 즉, var는 사용하지 않아야 하는 키워드
- 다만, 아직까지도 많은 기존의 JavaScript 코드는 ES6 이전의 문법으로 작성되어 있으므로 호이스팅에 대한 이해가 필요

# 변수 선언 키워드 정리

[사진]

- 어디에 변수를 쓰고 상수를 쓸지 결정하는 것은 프로그래머의 몫
- Airbnb 스타일 가이드에서는 기본적으로 const 사용을 권장
    - 재할당해야 하는 경우만 let
- 다만, 실습에서는 편의를 위해 재할당이 가능한 let을 기본적으로 사용해도 됨

# 데이터 타입
- JavaScript의 모든 값은 특정한 데이터 타입을 가짐
- 크게 원시 타입(Primitive type)과 참조 타입(Reference type)으로 분류됨

```
# Number
  - 정수 또는 실수형 숫자르 표현하는 자료형

# String
  - 문자열을 표현하는 자료형
  - 작은 따옴표 또는 큰 따옴표 모두 가능
  - 곱셈, 나눗셈, 뺄셈은 안되지만 덧셈을 통해 문자열을 붙일 수 있음
  - Quote를 사용하면 선언 시 줄 바꿈이 안됨
  - 대신 escqpe sequence를 사용할 수 있기 때문에 \n를 사용해야 함

  - Template Literal을 사용하면 줄 바꿈이 되며, 문자열 사이에 변수도 삽입도 가능
        (단, escape sequenct를 사용할 수 없다) == Python에서 f-string

# Empty Value
  - 값이 존재하지 않음을 표현하는 값으로 JavaScript에서는 null과 undefined가 존재
  - 동일한 역할을 하는 이 두개의 키워드가 존재하는 이유는 단순한 JavaScript의 설계 실수
  - 큰 차이를 두지 말고 interchangeable하게 사용할 수 있도록 권장함
        - null
            - null 값을 나타내는 특별한 키워드
            - '변수의 값이 없음을 의도적으로 표현할 때' 사용하는 데이터 타입
        - undefined
            - 값이 정의되어 있지 않음을 표현하는 값
            - 변수 선언 이후 '직접 값을 할당하지 않으면 자동으로 할당됨'

  - null과 defined의 가장 대표적인 차이점은 typeof 연산자를 통해 타입을 확인 했을 때 나타남
        - type null       //  "object"
        - type undefined  //  "undefined"
    
  - null이 원시 타입임에도 불구하고 object로 출력되는 이유는 JavaScript 설계 당시의 버그를 지금까지 해결하지 못한 것
  - 쉽게 해결 할 수 없는 이유는 이미 null 타입에 의존성을 띄고 있는 많은 프로그램들이 망가질 수 있기 때문 (하위 호환 유지)

# Boolean
  - true와 false
  - 참과 거짓을 표현하는 값
  - 조건문 또는 반복문에서 유용하게 사용
        - 조건문 또는 반복문에서 boolean이 아닌 데이터 타입은 '자동 형변환 규칙'에 따라 true와 false로 변환됨
```

### Template literals (템플릿 리터럴)
- 내장된 표현식을 허용하는 문자열 작성 방식
- ES6+ 부터 지원
- Backtick(``)을 이용하며, 여러 줄에 걸쳐 문자열을 정의할 수도 있고 JavaScript의 변수를 문자열 안에 바로 연결할 수 있는 이점이 생김
- 표현식을 넣을 수 있는데, 이는 $와 중괄호 ($ {expression}) 로 표기
```
const age = 10
const message = `홍길동은 ${age}세입니다.`
```

### ToBoolean Conversions (자동 형변환)

[사진]

# 연산자
```
# 할당 연산자
    - Python과 비슷
    - Increment 및 Decrement 연산자
        - Incrment(++) : 피연산자의 값을 1 증가시키는 연산자
        - Decrement(--) : 피연산자의 값을 1 감소시키는 연산자

    - += 또는 -= 와 같이 더 분명한 표현으로 적을 것을 권장

# 비교 연산자
    - Python과 비슷
    - 문자열은 유니코드 값을 사용하며 표준 사전 순서를 기반을 비교

# 동등 연산자 (==)
    - 두 피연산자가 같은 값으로 평가되는지 비교 후 boolean 값을 반환
    - 비교할 때 '암묵적 타입 변환'을 통해 타입을 일치시킨 후 같은 값인지 비교
    - 두 피연산자가 모두 객체일 경우 메모리의 같은 객체를 바라보는지 판별

    - 예상치 못한 결과가 발생할 수 있으므로 특별한 경우를 제외하고 사용하지 않음

# 일치 연산자 (===)
    - 두 피연산자의 값과 타입이 모두 같은 경우 true를 반환
    - 같은 객체를 가리키거나, 같은 타입이면서 같은 값이지를 비교
    - 엄격한 비교가 이뤄지며 암묵적 타입 변환이 발생하지 않음
        - 엄격한 비교 : 두 비교 대상의 타입과 값 모두 같은 지 비교하는 방식

# 논리 연산자
    - and는 '&&'
    - or는 '||'
    - not은 '!'
    - 단축 평가 지원

# 삼항 연산자 (Ternary Operator)
    - 3개의 피연산자를 사용하여 조건에 따라 값을 반환하는 연산자
    - 가장 앞의 조건식이 참이면 :(콜론) 앞의 값이 반환되며, 그 반대일 경우 : 뒤의 값이 반환되는 연산자
    - 삼항 연산자의 결과 값이기 때문에 변수에 할당 가능
```

# 조건문
- if statement
    - 조건 표현식의 결과값을 boolean 타입으로 변환 후 참/거짓을 판단
    
    - if, else if, else
        - 조건은 소괄호(condition) 안에 작성
        - 실행할 코드는 중괄호 {} 안에 작성
        - 블록 스코프 생성

- switch statement
    - 조건 표현식의 결과값이 어느 값(case)에 해당하는지 판별
    - 주로 특정 변수의 값에 따라 조건을 분기할 때 활용
        - 조건이 많아질 경우 if문보다 가독성이 나을 수 있음

    - 표현식(expression)의 결과값을 이용한 조건문
    - 표현식의 결과값과 case문의 오른쪽 값을 비교
    - break 및 default문은 '선택적'으로 사용 가능
    - break문이 없는 경우 break문을 만나거나 defalut문을 실행할 때까지 다음 조건문 실행
    - 블록 스코프 생성

- 조건이 많은 경우 switch문을 통해 가독성 향상을 기대할 수 있음
- 일반적으로 중첩 else if문은 유지보수하기 힘들다는 문제도 있음

# 반복문
```
반복문 종류
    - while
    - for
    - for...in
    - for...of


# while
    - 조건문이 참이기만 하면 문장을 계속해서 수행
        while (조건문) {
            // do something
        }
# for
    - 특정한 조건이 거짓으로 판별될 때까지 반복
        for ([초기문]; [조건문]; [증감문]) {
            // do something
        }

# for...in
    - 객체(object)의 속석을 순회할 때 사용
        - Key - Value 형태로 되어 있는 걸 JavaScript에서 객체라고 함 == Python의 Dictionary
        - 즉, 객체의 속성 값을 조회하는게 바로 for...in
    - 배열도 순회 가능하지만 인덱스 순으로 순회한다는 보장이 없으므로 권장하지 않음
        for (varialbe in object) {
            statements
        }

# for...of
    - 배열과 같이 반복 가능한 객체를 순회할 때 사용
    - 반복 가능한(interable) 객체의 종류 : Array, Set, String 등
        for (varialbe of object) {
            statement
        }
```
### for...in 과 for...of의 차이
- for...in은 속성 이름을 통해 반복  (객체 순회)
- for...of는 속성 값을 통해 반복    (Iterable 순회)

### [참고] for...in, for...of 와 const
- 일반적인 for문 for (let i = 0; i < arr.length; i++) {...}의 경우에는 최초 정의한 i를 재할당 하면서 사용하기 때문에 const를 사용하면 에러 발생
- 다만 for...in, for...of의 경우에는 재할당이 아니라, 매 반복 시 해당 변수를 새로 정의하여 사용하므로 에러가 발생하지 않음

# 조건문과 반복문 정리

[사진]


# 함수
- 참조 타입 중 하나로써 function 타입에 속함
- JavaScript에서 함수를 정의하는 방법은 주로 2가지로 구분됨
    - 함수 선언식 (function declaration)
    - 함수 표현식 (function expression)

### 함수 선언식
```
- 일반적인 프로그래밍 언어의 함수 정의 방식

function add(num1, num2) {
  return num1 + num2
}

console.log(add(2, 7))  // 9
```

### 함수 표현식
```
- 표현식 내에서 함수를 정의하는 방법
- 함수 표현식은 함수의 이름을 생략한 익명 함수로 정의 가능
- 표현식에서 함수 이름을 명시하는 것도 가능
- 다만 이 경우 함수 이름은 호출에 사용되지 못하고 디버깅 용도로 사용됨

const sub = function (num1, num2) {
  return num1 - num2
}

console.log(add(7, 2))  // 5
```

### 기본 인자(Default arguments)
- 인자 작성시 '=' 문자 뒤 기본 인자 선언 가능
```
const greeting = function (name) {
  return `Hi ${name}`
}
```

### 호이스팅 - 선언식
- 함수 선언식으로 정의한 함수는 var로 정의한 변수처럼 호이스팅 발생
- 즉 함수 호출 이후에 선언해도 동작
```
console.log(add(2, 7))  // 9

function add(num1, num2) {
  return num1 + num2
}
```
- 반면 함수 표현식으로 선언한 함수는 함수 정의 전에 호출 시 에러 발생
- 함수 표현식으로 정의된 함수는 변수로 평가되어 변수의 scope 규칙을 따름

# 화살표 함수 (Arrow Function)
- "함수를 비교적 간결하게 정의할 수 있는 문법"
- function 키워드와 중괄호를 이용한 구문을 짧게 사용하기 위해 탄생
    1. function 키워드 생략 가능
    2. 함수의 매개변수가 하나뿐이라면 '()' 도 생략 가능
    3. 함수의 내용이 한 줄이라면 '{}' 와 'return'도 생략 가능
- 화살표 함수는 항상 익명 함수
    - == 함수 표현식에서만 사용가능

```
const greeting = function (name) {
  return `Hi ${name}`
}

1. function 키워드 생략 가능
const greeting = (name) => {
  return `Hi ${name}`
}

2. 함수의 매개변수가 하나뿐이라면 '()' 도 생략 가능
const greeting = name => {
  return `Hi ${name}`
}

3. 함수의 내용이 한 줄이라면 '{}' 와 'return'도 생략 가능
const greeting = name => `Hi ${name}`

* 명확성과 일관성을 위해 항상 인자 주위에는 괄호 ('()')를 포함하는 것을 권장
```

# 즉시 실행 함수 (IIFE, Immediately Invoked Function Expression)
- 선언과 동시에 실행되는 함수
- 함수의 선언 끝에 '()'를 추가하여 선언되자 마자 실행하는 형태
- '()'에 값을 넣어 인자로 넘겨줄 수 있음
- 즉시 실행 함수는 선언과 동시에 실행되기 때문에 같은 함수를 다시 호출할 수 없음
- 이러한 특징을 살려 초기화 부분에 많이 사용
- 일회성 함수이므로 익명함수로 사용하는 것이 일반적
```
function (num) {return num ** 3}

(num) => { return num ** 3 }

((num) => num ** 3)(2)
```

# 배열(Array)
- 키와 속성들을 담고 있는 참조 타입의 객체
- 순서를 보장하는 특징이 있음
- 주로 대괄호([])를 이용하여 생성하고, 0을 포함한 양의 정수 인덱스로 특정 값에 접근 가능
- 배열의 길이는 array.length 형태로 접근 가능
    - (참고) 배열의 마지막 원소는 array.length -1로 접근
```
const numbers = [1, 2, 3, 4, 5]

console.log(numbers[0])         //  1
console.log(numbers[-1])        //  undefined
console.log(numbers.length)     //  5
console.log(numbers[numbers.length - 1])    //  5
```

# 배열 메서드 기초

[사진]

```
# array.reverse()
    - 원본 배열 요소들의 순서를 반대로 정렬
        numbers.reverse()
        console.log(numbers)

# array.push()
    - 배열의 가장 뒤에 요소 추가
        numbers.push(100)
        console.log(numbers)

# array.pop()
    - 배열의 마지막 요소 제거
        numbers.pop()
        console.log(numbers)

# array.includes(value)
    - 배열에 특정 값(value)이 존재하는지 판별 후 true 또는 false 반환
        console.log(numbers.includes(1))
        console.log(numbers.includes(100))

# array.indexof(value)
    - 배열에 특정 값이 존재하는지 확인 후 가장 첫 번째로 찾은 요소의 인덱스 반환
    - 만약 해당 값이 없을 경우 -1 반환
        console.log(numbers.indexOf(3))
        console.log(numbers.indexOf(100))

# array.join([separator])
    - 배열의 모든 요소를 연결하여 반환
    - separator(구분자)는 선택적으로 지정 가능하며, 생략 시 쉼표를 기본 값으로 사용
        console.log(numbers.join())
        console.log(numbers.join(''))
        console.log(numbers.join(' '))
        console.log(numbers.join('-'))
```

# 배열 메서드 심화
- 배열을 순회하며 특정 로직을 수행하는 메서드
- 메서드 호출 시 인자로 callback 함수를 받는 것이 특징
    - callback 함수 : 어떤 함수의 내부에서 실행될 목적으로 인자로 넘겨받는 함수

[사진]

### forEach
- 인자로 주어지는 함수(콜백 함수)를 배열의 각 요송 ㅔ대해 한 번씩 실행
    - 콜백 함수는 3가지 매개변수로 구성
        1. element : 배열의 요소
        2. index : 배열 요소의 인덱스
        3. array : 배열 자체
- 반환 값(return) 없음
```
// 1.
const colors = ['red', 'blue', 'green']

const printClr = function (color) {
  console.log(color)
}

colors.forEach(printClr)

// 2.
colors.forEach(function (color) {
  console.log(color)
})

// 3.
colors.forEach((color) => {
  console.log(color)
})

// 최종 단계
colors.forEach((color) => console.log(color))
```

### map
- 배열의 각 요소에 대해 콜백 함수를 한 번씩 실행
- 콜백 함수의 반환 값을 요소로 하는 새로운 배열 반환
- 기존 배열 전체를 다른 형태로 바꿀 때 유용
    - forEach + return이라고 생각하기
```
const numbers = [1, 2, 3, 4, 5]

const doubleEle = function (number) {
  return number * 2
}

const newArry = numbers.map(doubleEle)

console.log(newArry)

// 2.
const newArry = numbers.map(function (number) {
  return number * 2
})

// 3.
const newArry = numbers.map((number) => {
  return number * 2
})

// 4.
const newArry = numbers.map((number) => number * 2)
```

### filter
- 배열의 각 요소에 대해 콜백 함수를 한 번씩 실행
- 콜백 함수의 반환 값이 참인 요소들만 모아서 새로운 배열 반환
- 기존 배열의 요소들을 필터링할 때 유용
```
const products = [
  { name: 'cucumber', type: 'vegetable' },
  { name: 'banana', type: 'fruit' },
  { name: 'carrot', type: 'vegetable' },
  { name: 'apple', type: 'fruit' },
]

const fruitFilter = function (product) {
  return product.type === 'fruit'
}

const newArry = products.filter(fruitFilter)

console.log(newArry)


// 2.

const newArry = products.filter(function (product) {
  return product.type === 'fruit'
})

// 3. 
const newArry = products.filter((product) => {
  return product.type === 'fruit'
})

```

### reduce
- 인자로 주어지는 함수(콜백 함수)를 배열의 각 요소에 대해 한 번씩 실행해서, 하나의 결과 값을 반환
- 즉, 배열을 하나의 값으로 계산하는 동작이 필요할 때 사용(총합, 평균 등)
- map, filter 등 여러 배열 메서드 동작을 배부분 대체할 수 있음
- reduce 메서드의 주요 매개 변수
    - acc
        - 이전 callback 함수의 반환 값이 누적되는 변수
    - initialValue (optional)
        - 최초 callback 함수 호출 시 acc에 할당되는 값, defalut 값은 배열의 첫 번째 값
- reduce의 첫번째 매개변수인 콜백함수의 첫번째 매개변수(acc)는 누적된 값(전 단계 까지의 결과)
- reduce의 두번째 매개벼변수인 initialValue는 누적될 값의 초기값, 지정하지 않을 시 첫번째 요소의 값이 됨
* 빈 배열의 경우 initialValue를 제공하지 않으면 에러 발생
```
const numbers = [90, 80, 70, 100]

총합

const sumNum = numbers.reduce(function (result, number) {
  return result + number
}, 0)

console.log(sumNum)


const sumNum = numbers.reduce((result, number) => {
  console.log(result)
  return result + number
}, 0)


const avgNum = numbers.reduce((result, number) => result + number, 0) / numbers.length
```

### find
- 배열의 각 요소에 대해 콜백 함수를 한 번씩 실행
- 콜백 함수의 반환 값이 참이면, 조건을 만족하는 첫번째 요소를 반환
- 찾는 값이 배열에 없으면 undefined 반환
```
const avengers = [
  { name: 'Tony Stark', age: 45 },
  { name: 'Steve Rogers', age: 32 },
  { name: 'Thor', age: 40 },
]

const avenger = avengers.find((avenger) => {
  return avenger.name === 'Tony Stark'
})

console.log(avenger)
```

### some
- 배열의 요소 중 하나라도 주어진 판별 함수를 통과하면 참을 반환
- 모든 요소가 통과하지 못하면 거짓 반환
- 빈 배열은 항상 false 반환
```
const arr = [1, 2, 3, 4, 5]

// 1. 
const result = arr.find(function (elem) {
  return elem % 2 === 0
})

// 2. 
const result = arr.find((elem) => {
  return elem % 2 === 0
})


// 3. 
const result = arr.some((elem) => elem % 2 === 0) 

console.log(result)
```

### every
- 배열의 모든 요소가 주어진 판별 함수를 통과하면 참을 반환
- 하나의 요소라도 통과하지 못하면 거짓 반환
- 빈 배열은 항상 true 반환
```
// every
const newResult = arr.every((elem) => elem % 2 === 0) 

console.log(newResult)
```

# 객체(Object)
- 객체는 속성(property)의 집합이며, 중괄호 내부에 key와 value의 쌍으로 표현
- key는 문자열 타입만 가능
    - key 이름에 띄어쓰기 등의 구분자가 있으면 따옴표로 묶어서 표현
- value는 모든 타입(함수 포함) 가능
- 객체 요소 접근은 점(.) 또는 대괄호([])로 가능
    - key 이름에 띄어쓰기 같은 구분자가 있으면 대괄호 접근만 가능
```
const myInfo = {
  name: 'jack',
  phoneNumber: '123456',
  'samsung product': {
    buds: 'Buds pro',
    galaxy: 'S99',
  },
}

console.log(myInfo.name)
console.log(myInfo['name'])

console.log(myInfo['samsung product'])
console.log(myInfo['samsung product'].galaxy)
```

# 객체 관련 문법
- ES6에 새로 도입된 문법들로 객체 생성 및 조작에 유용하게 사용 가능
    1. 속성명 축약
        - 객체를 정의할 때 key와 할당하는 변수의 이름이 같으면 예시와 같이 축약 가능

    2. 메서드명 축약
        - 메서드 선언 시 function 키워드 생략 가능
            ```
            const obj = {
            name: 'jack',
            greeting() {
                console.log('hi!')
            }
            }

            console.log(obj.name)
            console.log(obj.greeting())
            ```

    3. 계산된 속성명 사용하기
        - 객체를 정의할 때 key의 이름을 표현식을 이용하여 동적으로 생성 가능
            ```
            const key = 'ssafy'
            const value = ['한국', '미국', '일본', '중국']

            const myObj = {
            [key]: value,
            }
            ```
    4. 구조 분해 할당
        - 배열 또는 객체를 분해하여 속성을 변수에 쉽게 할당할 수 있는 문법
        
    5. 객체 전개 구문(Spread Operator)
        - 배열과 마찬가지로 전개구문을 사용해 객체 내부에서 객체 전개 가능
        - 얕은 복사에 활용 가능

### JSON
- JavaScript Object Notation
- Key-Value 형태로 이루어진 자료 표기법
- JavaScript의 Object와 유사한 구조를 가지고 있지만 Object는 그 자체로 타입이고, JSON은 형식이 있는 "문자열"
- 즉, JSON을 Object로 사용하기 위해서는 변환 작업이 필요
```
const jsonData = {
  coffee: 'Americano',
  iceCream: 'Mint Choco',
}

// Object -> json
const objToJson = JSON.stringify(jsonData)

console.log(objToJson)  // {"coffee":"Americano","iceCream":"Mint Choco"}
console.log(typeof objToJson)  // string


// json -> Object
const jsonToObj = JSON.parse(objToJson)  // { coffee: 'Americano', iceCream: 'Mint Choco' }
console.log(jsonToObj)
console.log(typeof jsonToObj)  // object
console.log(jsonToObj.coffee)  // Americano
```

### [참고] 배열은 객체다
- 배열은 키와 속성들을 담고 있는 참조 타입의 객체
- 배열은 인덱스를 키로 가지며 length property를 갖는 특수한 객체