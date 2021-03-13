<template>
  <div id="login">
        <!-- <h3 class="text-center text-white pt-5">Login form</h3> -->
        <div class="container-login">
            <div id="login-row" class="row-login justify-content-center align-items-center">
                <div id="login-column" class="col-md-6">
                    <div id="login-box" class="col-md-12">
                        <form @submit.prevent="login" id="login-form" class="form-login" action="" method="post">
                            <h3 class="text-center text-info">Login</h3>
                            <div class="form-group">
                                <label for="email" class="text-info">Email:</label><br>
                                <input type="text" name="email" v-model="email" class="form-control">
                            </div>
                            <div class="form-group">
                                <label for="password" class="text-info">Password:</label><br>
                                <input type="text" name="password" v-model="password" class="form-control">
                            </div>
                            <div class="form-group">
                                <input type="submit" name="submit" class="btn btn-info btn-md" value="submit">
                            </div>
                            <div id="register-link" class="text-right">
                                <a href="#" class="text-info">Register here</a>
                            </div>
                        </form>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            email: '',
            password: ''
        }
    },
    methods: {
        login() {
            this.$emit('emitLogin', this.email, this.password)
        }
    }
}
</script>

<style>
#login .container-login #login-row #login-column #login-box {
  margin-top: 120px;
  max-width: 600px;
  height: 450px;
  border: 1px solid #9C9C9C;
  background-color: #EAEAEA;
  border-radius: 12px;
  top: 50%;
  left: 50%;
}
#login .container-login #login-row #login-column #login-box #login-form {
  padding: 20px;
}
#login .container-login #login-row #login-column #login-box #login-form #register-link {
  margin-top: -50px;
}
</style>