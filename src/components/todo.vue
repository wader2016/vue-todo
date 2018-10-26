<template>
  <section class="real-app">
    <input 
      type="text"
      class="add-input"
      autofocus="autofocus"
      placeholder="接下去要做什么？"
      @keyup.enter="addTodo"
    >
     <item 
        :todo = "todo"
        v-for="todo in CalculateTodo"
        :key="todo.id"  
        @del = "deleteTodo"
      >
     </item>
     <tabs 
        :filter="filter"
        :todos="todos" 
        @toggleFilter = "toggleFilter"
        @clearAll = "clearAllCompleted"     
     ></tabs>
  </section>
 
</template>

<script>
import Item from './item'
import Tabs from './tabs'
let id = 0;
  export default {
    data () {
      return {
        todos : [],
        filter:'all'
      }
    },
    components:{
      Item,
      Tabs
    },
    computed:{
      CalculateTodo () {
        if(this.filter === 'all'){
          return this.todos;
        }
        const completed = this.filter === 'completed';
         return this.todos.filter(todo => todo.completed === completed);
      }
    },
    methods:{
      addTodo(e) {   
        let item = {
            id:id++,
            content:e.target.value,
            completed:false
        }
        this.todos.unshift(item);
        e.target.value = '';
      },
      deleteTodo(id) {
        this.todos.splice(this.todos.findIndex(todo=>todo.id === id), 1);
      },
      toggleFilter(state) {
        this.filter = state;
      },
      clearAllCompleted() {
        this.todos = this.todos.filter(todo => !todo.completed);
      }
    }
  }
</script>

<style scoped>
  .real-app {
    width: 600px;
    margin: 0 auto;
    box-shadow: 0 0 5px #666;
  }
  .add-input {
    position: relative;
    margin: 0;
    width: 100%;
    font-size: 24px;
    line-height: 1.4em;
    border: none;
    outline: none;
    padding: 16px 16px 16px 60px;
    box-sizing: border-box;
    box-shadow: 0 -2px 1px rgba(0, 0, 0, 0.1);

  }
</style>

