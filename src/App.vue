<template>
  <div id="app">
    <img class="logo" src="./assets/logo.png">
    <component :is="currentComponent"></component>
    <hr>
    <div class="btn-group btn-block">
      <button @click="currentComponent = 'login'" class="btn btn-success">Login</button>
      <button @click="currentComponent = 'register'" class="btn btn-primary">Register</button>
      <button @click="currentComponent = 'stories'" class="btn btn-info">Stories</button>
    </div>
  </div>
</template>

<script>
import Login from './components/Login'
import Register from './components/Register'
import Stories from './components/Stories'

export default {
  name: 'App',
  components: {
    Login,
    Register,
    Stories
  },
  data () {
    return {
      currentComponent: 'login'
    }
  }
}
</script>

<style>
html {
  height: 100%;
}

body {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
}

#app {
  color: #2c3e50;
  margin-top: -100px;
  max-width: 600px;
  font-family: Source Sans Pro, Helvetica, sans-serif;
  text-align: center;
}

#app a {
  color: #42b983;
  text-decoration: none;
}

.logo {
  width: 100px;
  height: 100px
}
</style>
