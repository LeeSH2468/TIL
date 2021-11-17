# ES6

## ECMAScript6

### ES6란?

ECMAScript의 최신버전으로 es6로 줄여 부른다. es5에서 새로운 기능들이 추가됐다



### 화살표함수(Arrow functions)

- [MDN 화살표함수](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Functions/Arrow_functions)

```javascript
// es5
function test(a){
    return a + 'bcde';
}
consonle.log(tset('Z'));

// Zbcde 출력
```

```javascript
// es6
const test = (a) => { return `${a}bcde` }
console.log(test('Z'))

// Zbcde 출력
```





### let과 const

- `var`처럼 변수 선언을 위한 키워드. `var`는 호이스팅이 일어나기 때문
- `const` : 변경 불가능한 변수
- `let` : 변경 가능한 변수



### 템플릿 문자열(Template Literals)

- 백틱(`)을 이용해 문자열 내에서 변수 사용
- `백틱 사이에 ${변수사용}`



### 기본매개변수(Default parameters)

- 변수의 기본값 설정. undefined가 나오지 않도록 기본값 설정

```javascript
const test = (teset1, test2 = 2) => {
    return 
}

// test2 값을 입력하지 않아도 기본값 2 출력
```



### 배열,객체 비구조화(Array and object destructing)





### 가져오기, 내보내기(Import, export)

### 프로미스(Primises)

### 나머지 매개변수 및 확산연산자(Rest parameter and Spread operator)

### 클래스(Classes)