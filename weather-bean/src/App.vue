<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/bean-sprout.png">
    <h1> Weather Bean </h1>
    <Input v-model="city" @keydown.enter="serch"/>
  </div>
</template>

<script>
import Input from './components/Input';
export default {
  name: 'app',
  components: {
    Input
  }
}
</script>

<style>
#app {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  background: #F7F7F7;
}
img {
  width: 15%;
  height: auto;
}
#mapid { height: 180px; }
</style>


