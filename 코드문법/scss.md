# scss



## each

```
@each $변수 in 데이터 {
	실행문
}
```



### list 데이터 반복

- 배열(array) 생성 : $배열명 : (배열1, 배열2)
- 배열 선언 : $항목 in $배열명{ #{$항목}}
- 배열에 기호작성 불가(따옴표로 묶어서 표기 불가)

```scss
$lists : (red, orange, yellow ,green);

@each $listname in $lists{
    li.#{$listname}{
        background-color: #{$listname};
    }
}
```

- css 컴파일 결과물

```css
li.red {
  background-color: red;
}

li.orange {
  background-color: orange;
}

li.yellow {
  background-color: yellow;
}

li.green {
  background-color: green;
}
```

  



### map 데이터 반복

- 2차식배열
- 배열에 따옴표 및 특수문자 사용 가능

```scss
$colors: (
    test1 : '#aaa',
    test2 : '#bbb',
    test3 : '#ccc'
);

@each $test, $color in $colors {
    div.#{$test}{
        color: #{$color};
    }
}
```

- css컴파일 결과물

```css
div.test1 {
  color: #aaa;
}

div.test2 {
  color: #bbb;
}

div.test3 {
  color: #ccc;
}
```





## 코멘트

- 컬러 작성시 # 기호를 사용하려면 2차식 배열(map을 사용해야한다)
