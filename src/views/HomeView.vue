<template>
  <!-- <div :class="theme == 'dark' ? 'home-dark' : 'home-lihgt'"> -->
  <div class="home-light">
    <NavBar :userLogin = "userLogin"/>
    <h1 class="home-title" align="center">Gamor</h1>
    <MainSection :theme = "theme"/>
    <CategorySection :theme = "theme"/>
  </div>
</template>

<script>
import NavBar from '@/components/Navbar'
import CategorySection from '@/components/CategorySection'
import MainSection from '@/components/MainSection'
import Cookies from "js-cookie";

export default {
  name: 'HomeView',
  components: {
    NavBar,
    CategorySection,
    MainSection
  },
  data () {
    return {
     userLogin: '' ,
     theme: ''
    }
  },
  created(){
    this.userLogin = Cookies.get('userLogin');
    console.log('this.theme', this.theme)
  }
}
</script>
