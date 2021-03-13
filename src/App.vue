<template>
<div>
  <Login></Login>
  <Home></Home>
  <Register></Register>
</div>
</template>

<script>
import Login from './views/Login'
import Home from './views/Home'
import Register from './views/Register'

export default {
  components: {
      Login,
      Home,
      Register
  }
};
</script>

<style scoped>
</style>


