<template>
  <div id="app">
    <div class="container">
      <img class="logo" src="./assets/logo.png">
      <h1>Welcome to dynamic Components!</h1>
      <ul class="nav nav-tabs">
        <li v-for="page in pages" :key="page" class="nav-item">
          <a @click="setPage(page)" href="#" class="nav-link" :class="isActivePage(page) ? 'active' : ''">{{ page | capitalize }}</a>
        </li>
      </ul>
      <component :is="activePage"></component>
    </div>
  </div>
</template>

<script>
import Vue from 'vue'
import Login from './components/Login'
import Register from './components/Register'
import Stories from './components/Stories'

Vue.filter('capitalize', value => {
  return value.charAt(0).toUpperCase() + value.substr(1)
})

export default {
  name: 'App',
  components: {
    Login,
    Register,
    Stories
  },
  data () {
    return {
      pages: [
        'login',
        'stories',
        'register'
      ],
      activePage: 'login'
    }
  },
  methods: {
    setPage (page) {
      this.activePage = page
    },
    isActivePage (page) {
      return this.activePage === page
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

.logo {
  width: 100px;
  height: 100px
}
</style>
