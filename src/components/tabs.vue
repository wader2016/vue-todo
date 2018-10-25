<template>
  <div class="helper">
    <span class="left">2 item left</span>
    <span class="tabs">
      <span 
        v-for="state in states" 
        :key="state" 
        :class="[state,filter === state ? 'actived' : '' ]"
        @click="toggleFilter(state)"
      >
        {{state}}
      </span>
    </span>
    <span class="clearCompleted" @click="clearCompleted">
      clear completed
    </span>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        states : ['all','active','completed']
      }
    },
    props:{
      filter:{
        type : String,
        required:true
      }
    },
    methods:{
      toggleFilter(state) {

      },
      clearCompleted() {

      }
    }
  }
</script>

<style scoped>
  .helper {
    background-color: #fff;
    display: flex;
    padding: 5px 0;
    line-height: 30px;
    font-weight: 100;
    justify-content: space-between;
    font-size: 14px;
  }
  .left {
    text-align: left;
    width: 150px;
    padding: 0 10px;
    box-sizing: border-box;
  }
  .clearCompleted {
    text-align: right;
    width: 150px;
    cursor: pointer;
    padding: 0 10px;
    box-sizing: border-box;
  }
  .tabs {
    width: 200px;
    display: flex;
    justify-content: space-around;
    padding: 0 10px;
    box-sizing: border-box;

  }
  .tabs > span {
    display: inline-block;
    padding: 0 10px;
    cursor: pointer;

  }
  .tabs >  .actived {
    border-radius: 5px;
    border: 1px solid rgba(0, 0, 0, 0.6);
  }
</style>
