<template>
  <div class="category-section">
    <h3 class="title-section">Trending Categories</h3>
    <div class="card-category" v-for="(item, index) in listGame" :key="index">
      <img :src="item.img" class="category-img">
      <div class="div-encima">
        <div class="div-info">
          <div v-if="item.id !== '00'">
            <span class="category-separator">/</span>
            <span class="category-id">{{item.id}}</span>
          </div>
          <div v-else>
            <span class="category-id">{{item.name}}</span>
          </div>
          <div class="category-title">
            <span>{{item.category}}</span>
          </div>
          <div class="category-title">
            <span>icon</span>
          </div>
        </div>       
      </div>      
    </div>  
  </div>
</template>

<script>
export default {
  name: 'CategorySection', 
  data () {
    return {
      listGame: [
        {
          id: '01',
          name: 'Elden Ring',
          category: 'Action Games',
          img: '/img/games/elden-ring.jpg'
        },
        {
          id: '02',
          name: 'Fifa 23',
          category: 'Sports Games',
          img: '/img/games/fifa-23.jpg'
        },
        {
          id: '03',
          name: 'God of War',
          category: 'Adventure Games',
          img: '/img/games/god-war.jpg'
        },   
        {
          id: '04',
          name: 'Pac Man',
          category: 'Arcade Games',
          img: '/img/games/pac-man.png'
        },       
        {
          id: '05',
          name: 'Wizard101',
          category: 'Fantasy Games',
          img: '/img/games/wizard101.jpg'
        },
        {
          id: '06',
          name: 'XCOM 2',
          category: 'Strategy Games',
          img: '/img/games/xcom-2.jpg'
        },
        {
          id: '07',
          name: 'Fortnite',
          category: 'Shooter Games',
          img: '/img/games/fortnite.jpg'
        },            
        {
          id: '00',
          name: 'VIEW ALL',
          category: 'All categories',
          img: '/img/games/all-categories.jpg'
        }              
      ]
    }
  },
}
</script>
