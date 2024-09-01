<template>
  <Login />
</template>
<script>
import Login from './components/Login.vue'
//import TestVue from './components/TestVue.vue'
//import DianJi from './components/DianJi.vue'
export default {
  name: 'App',
  components: {
    Login
  }
}
</script>

<style>
*{
  margin: 0 0;
  padding: 0 0;
  user-select: none;
}
#app {
  width: 100vw;
  height: 100vh;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
