<template>
  <div id="register">
        <div class="container-register">
            <div id="register-row" class="row-register justify-content-center align-items-center">
                <div id="register-column" class="col-md-6">
                    <div id="register-box" class="col-md-12">
                        <form @submit.prevent="register" id="register-form" class="form-register" action="" method="post">
                            <h3 class="text-center text-info">Register</h3>
                            <div class="form-group">
                                <label for="email" class="text-info">Email:</label><br>
                                <input type="text" name="email" id="email" class="form-control">
                            </div>
                            <div class="form-group">
                                <label for="password" class="text-info">Password:</label><br>
                                <input type="text" name="password" id="password" class="form-control">
                            </div>
                            <div class="form-group">
                                <input type="submit" name="submit" class="btn btn-info btn-md" value="submit">
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
    name: 'Register'
}
</script>

<style>
#register .container-register #register-row #register-column #register-box {
  margin-top: 120px;
  max-width: 600px;
  height: 450px;
  border: 1px solid #9C9C9C;
  background-color: #EAEAEA;
  border-radius: 12px;
  top: 50%;
  left: 50%;
}
#register .container-register #register-row #register-column #register-box #register-form {
  padding: 20px;
}
#register .container-register #register-row #register-column #register-box #register-form #register-link {
  margin-top: -50px;
}
</style>