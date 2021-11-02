# Vue.js

[vue 공식 사이트](https://kr.vuejs.org/)



## 설치

```
npm install --global @vue/cli
```
```
vue --version  // 뷰 버전확인(설치확인)
```



## 시작

```
vue create 폴더명  // 작업폴더 생성
cd 폴더명          // 폴더로 경로이동
npm run serve     // 서버실행
```



## 세팅

터미널 새로 오픈시 경로 확인(생성한 폴더 내부에서 작업)

### 1. 라우터 설치

```
npm i vue-router --save
```
설치확인 : package.json파일에서 vue-router이 추가되었는지 확인

 ```
 "dependencies": {
    "vue-router": "^3.5.2"
  }
 ```



### 2. vutify

- Vue에서 가장 많이 사용되는 UI toolkit



## 기초문법

### v-for

반복문 

```
<div id="test">
	<ul>
		<li v-for="todo in todos">
			{{ todo.text }}
		</li>
	</ul>	
</div>
```



### v-if / v-else

조건문

- 반드시 v-if 와 v-else가 연달아 있어야함

```
<template v-if="item.domain">
  <a v-bind:href="item.url">
      {{ item.title }}
  </a>
</template>

<template v-else>
  <router-link :to="`item/${item.id}`"> 
      {{ item.title }}
  </router-link>
</template>
```

