<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/bean-sprout.png">
    <h1> Weather Bean </h1>
    <Homepage v-bind:city="city" />
  </div>
</template>

<script>
import Homepage from './components/Homepage';
export default {
  name: 'app',
  components: {
    Homepage
  },
  data(){
    return {
      city: [
        {
          id: 0,
          title: "new orleans",
          time: 10
        },
        {
          id: 1,
          title: "baton rouge",
          time: 2
        }
      ]
    }
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
</style>
