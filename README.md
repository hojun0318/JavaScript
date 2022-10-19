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