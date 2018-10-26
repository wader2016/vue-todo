<template>
  <div id="app">
    <div id="cover"></div>
    <Header></Header>
    <todo></todo>
    <Footer></Footer>
  </div>
</template>

<script>

import Header from './components/Header'
import Footer from './components/Footer'
import Todo from './components/todo'

export default {
  name: 'App',
  components: {
    Header,
    Footer,
    Todo 
  }
}
</script>

<style>
#app {
  position:absolute;
  top:0;
  bottom: 0;
  left: 0;
  right: 0;
}
#cover {
  position:absolute;
  top:0;
  bottom: 0;
  left: 0;
  right: 0;
  opacity: 0.6;
  background-color: #888;
  z-index: -1;
}
</style>
