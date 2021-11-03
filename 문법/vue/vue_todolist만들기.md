# vue.js

## todolist 만들기

참고 : [캡틴판교 인강 - 인프런](https://www.inflearn.com/course/vue-pwa-vue-js-%EC%A4%91%EA%B8%89/dashboard)

### 0. 파일구조

```
src 
 ├ components 
 │	├ TodoBtn.vue
 │	├ TodoInput.vue
 │	├ TodoList.vue
 │	├ TodoTitle.vue
 │
 ├ App.vue
 └ main.js
 
```



### App.vue

- 전체적 구조 만들기

  ```
  <template>
      <TodoTitle></TodoTitle>
      <TodoInput></TodoInput>
      <TodoList></TodoList>
      <TodoBtn></TodoBtn>
  </template>
  ```

- 불러오기

  ```
  <script>
  import TodoTitle from './components/TodoTitle.vue'
  import TodoInput from './components/TodoInput.vue'
  import TodoList from './components/TodoList.vue'
  import TodoBtn from './components/TodoBtn.vue'
  
  export default {
    data(){
      return {
        todoItems: []
      }
    },
    methods: {
  
    },
    components : {
      TodoTitle,
      TodoInput,
      TodoList,
      TodoBtn
    }
  }
  </script>
  ```

  



### main.js

- 기본 선언(vue)

  ```
  import { createApp } from 'vue'
  import App from './App.vue'
  
  createApp(App).mount('#app')
  ```



### components  내부

#### TodoBtn.vue

- 전체삭제 기능

- localStorage.clear() - 로컬스토리지 내부 항목 전체삭제

  ```
  <template>
      <button type="submit" v-on:click="clearTodo">Clear All</button>
  </template>
  <script>
  export default {
      methods: {
          clearTodo: function(){
              localStorage.clear();
          }
      }
  }
  </script>
  ```

  



#### TodoInput.vue

- 등록내용(input), 등록버튼

- 로컬스토리지에 저장되는 함수 선언

- 클릭, 엔터 - 저장함수 실행

  - v-on:click="함수" - 클릭
  - v-on:keyup.enter="함수" - 엔터

- localStorage.setItem() - 로컬스토리지에 저장

  ```
  <template>
      <input type="text" v-model="newTodoItem" v-on:keyup.enter="addTodo">
       <button v-on:click="addTodo">add</button>
  </template>
  
  <script>
  export default {
      data : function(){
          return{
              newTodoItem: ""
          }
      },
      methods: {
          addTodo: function(){
              if(this.newTodoItem !== ''){
              var obj = {completed: false, item: this.newTodoItem};
              localStorage.setItem(this.newTodoItem, JSON.stringify(obj));
              this.clearInput();
              }
          },
          clearInput: function(){
              this.newTodoItem = ""; // 초기화
          }
      }
  }
  </script>
  ```

  

#### TodoList.vue

- 추가버튼 클릭시 항목 자동 생성

- *v-for*="todoItem in todoItems"

- todoItems - 빈 배열 생성

  ```
  <template>
      <ul>
          <li v-for="todoItem in todoItems" :key="todoItem">
              <input type="checkbox" :class="{checkBtnCompleted: todoItem.completed}" v-on:click="toggleComplate({todoItem,index})"/>
              {{ todoItem }}
              <span class="removeBtn" v-on:click="removeTodo(todoItem, index)">X</span>
          </li>
      </ul>
  </template>
  <script>
  export default {
      data : function(){
          return {
              todoItems: []
          }
      },
      methods: {
          removeTodo: function(todoItem, index) {
              localStorage.removeItem(todoItem);
              this.todoItems.splice(index,1);
          },
          toggleComplate: function(todoItem, index){
              console.log(todoItem, index)
          }
      },
      created: function() {
          if(localStorage.length > 0 ) {
              for(var i = 0; i < localStorage.length; i++){
                  if(localStorage.key(i) !== 'loglevel:webpack-dev-server'){
                      this.todoItems.push(localStorage.key(i));
                  }
              }
          }
      }
  }
  </script>
  ```



#### TodoTitle.vue

- 제목

  ```
  <template>
      <h1>To do it!</h1>
  </template>
  ```

  



