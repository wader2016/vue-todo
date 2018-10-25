<template>
  <section class="real-app">
    <input 
      type="text"
      class="add-input"
      autofocus="autofocus"
      placeholder="接下去要做什么？"
      @keyup.enter="addTodo"
    >
     <item :todo = "todo"></item>
     <tabs :filter="filter"></tabs>
  </section>
 
</template>

<script>
import Item from './item'
import Tabs from './tabs'
  export default {
    data () {
      return {
        todo : {
          id:0,
          content:"this is todo",
          completed:false
        },
        filter:'all'
      }
    },
    components:{
      Item,
      Tabs
    },
    methods:{
      addTodo() {

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

