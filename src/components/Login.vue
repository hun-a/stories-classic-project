<template>
  <div id="login">
    <h2>Sign in</h2>
    <form class="form-group">
      <input class="form-control" type="email" placeholder="Email adderss" autocomplete="username">
      <input class="form-control" type="password" placeholder="Password" autocomplete="current-password">
      <button class="btn btn-primary">Sign in</button>
    </form>
  </div>
</template>

<script>
export default {
  created () {
    console.log('login')
  }
}
</script>
