<template>
  <div class="login">
    <h2>Sign In</h2>
    <form class="form-login" v-on:submit.prevent="submit()">
      <div class="label-login">
        <span>Email</span>
      </div>
      <div class="input-login">
        <input type="email" v-model="form.email" required>
      </div>
      <div class="label-login">
        <span>Password</span>
      </div>
      <div class="input-login">
        <input type="password" v-model="form.password" required>
      </div>
      <div class="btn-login">
        <button type="submit">Sign In</button>
      </div>
    </form> 
  </div>
</template>

<script>
import Cookies from "js-cookie";

export default {
  name: 'LoginView',
  data () {
    return {
      user:{
        name: 'Gamor',
        email: 'gamor@gmail.com',
        password: 'gamor*2022'
      },
      form:{
        email: '',
        password: ''
      }      
    }
  },
  methods:{
    submit(){
      let result = this.form.email != this.user.email 
                  ? alert('Wrong email!')
                  : this.form.password != this.user.password
                  ? alert('Wrong password!')
                  : true
      if (result){
        //info('User successfully logged in!')
        Cookies.set('userLogin', result);
        this.$router.push({ 
          name: 'home',
        })
      }
    }
  }
}
</script>
