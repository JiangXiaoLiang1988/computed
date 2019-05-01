<template>
  <div id="app">
    <!-- <img src="./assets/logo.png">
    <router-view/> -->
    <!-- <Test></Test> -->
    <!-- <ComputedDemo></ComputedDemo> -->
    <!-- <ComputedDemo2></ComputedDemo2> -->
    <watchDemo></watchDemo>
  </div>
</template>

<script>
import Test from './components/Test'
import ComputedDemo from './components/ComputedDemo'
import ComputedDemo2 from './components/ComputedDemo2'
import watchDemo from './components/watchDemo'
export default {
  name: 'App',
  components:{
    Test,
    ComputedDemo,
    ComputedDemo2,
    watchDemo
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
