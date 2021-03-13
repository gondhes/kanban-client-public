<template>
<div>
  <Login v-if="!isLogin" @emitLogin='login'></Login>
  <Home v-if="isLogin"></Home>
  <!-- <Register></Register> -->
</div>
</template>

<script>
import Login from './views/Login'
import Home from './views/Home'
import Register from './views/Register'
import axios from 'axios'

export default {
  data() {
    return {
      isLogin: false,
      errorMsg: '',
      tasks: []
    }
  },
  components: {
      Login,
      Home,
      Register
  },
  created() {
    if (localStorage.access_token) {
      this.isLogin = true
    } else {
      this.isLogin = false
    }
  },
  methods: {
    login(email, password) {
      axios({
        method: 'POST',
        url: 'http://localhost:3000/login',
        data: {
            email,
            password
        }
      })
      .then(response => {
        localStorage.setItem('access_token', response.access_token)
        localStorage.setItem('userId', response.id)
        this.isLogin = true
      })
      .catch(err => {
        this.errorMsg = 'Invalid email/password'
        this.isLogin = false
      })
    },
    fetchTask() {
      axios({
        method: 'GET',
        url: 'http://localhost:3000/tasks'
      })
      .then(response => {
        this.tasks = response.data
      })
      .catch(err => {
        console.log(err)
      })
    }
  }
};
</script>

<style scoped>
</style>


