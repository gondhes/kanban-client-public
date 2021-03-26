<template>
<div>
  <Login v-if="!isLogin" @emitLogin='login' @googleLogin="googleLogin"></Login>
  <Home v-if="isLogin"></Home>
  <!-- <Register></Register> -->
</div>
</template>

<script>
const baseURL = 'http://localhost:3000'
// const baseURL = 'https://damp-shelf-32025.herokuapp.com/'
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
        url: baseURL + '/login',
        data: {
            email,
            password
        }
      })
      .then((response) => {
        localStorage.setItem('access_token', response.data.access_token)
        localStorage.setItem('userId', response.data.id)
        this.isLogin = true
      })
      .catch(err => {
        this.errorMsg = 'Invalid email/password'
        this.isLogin = false
      })
    },
    googleLogin(obj) {
      const token = obj.getAuthResponse().id_token;
      axios({
        method: 'POST',
        url: baseURL + '/googleLogin',
        data: {
            access_token : token
        }
      })
      .then((response) => {
        localStorage.setItem('access_token', response.data.access_token)
        localStorage.setItem('userId', response.data.id)
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
        url: baseURL + '/tasks'
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


