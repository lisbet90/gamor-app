<template>
  <!-- <nav :class="theme == 'dark' ? 'navbar-dark' : 'navbar-lihgt'"> -->
  <nav class="navbar-light">
    <ul class="navbar-menu">
      <li class="menu-icon" @click="open = !open"><a><i class="fa fa-bars"></i></a></li>
      <div class="dropdown-menu" :class="open ? 'dropdown-menu-open':'dropdown-menu-close'">
        <li class="item-menu"><a href="/">Home</a></li>
        <li class="item-menu"><a href="#">Streams</a></li>
        <li class="item-menu"><a href="#">Party</a></li>
        <li class="item-menu"><a href="#">Premium</a></li>
        <li class="item-menu">
          <div class="dropdown">
            <button class="dropbtn-simple">Theme  
              <i class="fa fa-caret-down"></i>  
            </button>
            <div class="dropdown-content">
              <a href="#" @click="changeTheme('dark')">Dark</a>
              <a href="#" @click="changeTheme('light')">Light</a>
            </div>
          </div> 
        </li>
        <li class="btn-register" v-if="!userLogin"><a>Create account</a></li>
        <li class="btn-login" v-if="!userLogin"><a href="/login">Sign in</a></li>
        <li class="btn-login-icon" v-if="userLogin">
          <div class="dropdown">
            <button class="dropbtn">    
              <i class="fa fa-user"></i>  
            </button>
            <div class="dropdown-content">
              <a @click="logout()" style="cursor:pointer;">Logout</a>
              <a href="#">Change Password</a>
            </div>
          </div> 
        </li>
        <li class="btn-logout" v-if="userLogin && open" @click="logout()"><a>Logout</a></li>
        <li class="btn-pass" v-if="userLogin && open"><a href="#">Change Password</a></li>
      </div>
    </ul> 
  </nav>
</template>

<script>
import Cookies from "js-cookie";

export default {
  name: 'NavBar',
  props: {
    userLogin: Boolean
  },
  data(){
    return{
      open: false,
      theme: 'light'
    }
  },
  created(){
  },
  methods: {
    logout(){
      Cookies.remove('userLogin')
      this.$router.push({ 
          name: 'login',
        })
    },
    changeTheme(theme){
        this.theme = theme
    }
  }  
}
</script>

