<template>
  <div class="home">
    <NavBar/>
    <h1 class="home-title" align="center">Gamor</h1>
    <MainSection/>
    <CategorySection/>
  </div>
</template>

<script>
import NavBar from '@/components/Navbar'
import CategorySection from '@/components/CategorySection'
import MainSection from '@/components/MainSection'

export default {
  name: 'HomeView',
  components: {
    NavBar,
    CategorySection,
    MainSection
  }
}
</script>
