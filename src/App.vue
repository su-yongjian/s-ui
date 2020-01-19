<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <s-buttom @click="handleBtn">saf</s-buttom>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import SButtom from './components/s-buttom/s-buttom'
export default {
  name: 'app',
  components: {
    HelloWorld,
    SButtom
  },
  methods: {
    handleBtn (e) {
      console.log(e)
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
