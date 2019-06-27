<template>
  <div id="app">
    <div class="container">
      <img class="logo" src="./assets/logo.png">
      <h1>Welcome to Routing!</h1>
      <router-link :to="{ name: 'home' }" exact>Home</router-link>
      <router-link :to="{ name: 'login' }">Login</router-link>
      <router-link :to="{ name: 'register' }">Register</router-link>
      <router-link :to="{ name: 'stories.all' }">Stories</router-link>
      <transition name="fade">
        <router-view></router-view>
      </transition>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App'
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

.logo {
  width: 100px;
  height: 100px
}

.router-link-active {
  color: green;
}

.fade-enter {
  opacity: 0;
}

.fade-enter-active {
  transition: opacity 1s;
}

.fade-enter-to {
  opacity: 0.8;
}
</style>
