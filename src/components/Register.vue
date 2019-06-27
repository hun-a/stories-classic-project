<template>
  <div id="register">
    <h2>Register Form</h2>
    <input placeholder="First Name" class="form-control">
    <input placeholder="Last Name" class="form-control">
    <input placeholder="Email address" class="form-control">
    <input placeholder="Pick a password" class="form-control">
    <input placeholder="Confirm password" class="form-control">
    <button class="btn btn-primary btn-block">Sign up</button>
  </div>
</template>

<script>

export default {
  props: ['stories'],
  created () {
    console.log('register')
  }
}
</script>
