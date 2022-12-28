<template>
  <div :class="theme === 'dark' ? 'main-section-dark' : 'main-section-light'">
    <div class="principal-panel">
      <div class="left-panel">
        <div class="content-principal">
          <h1>start</h1>
          <h1 class="text-diferent">streaming</h1>
          <h1>games</h1>
          <h1>differently</h1>
        </div>
        <div class="content-second">
          <p>gamor now has <span class="text-diferent">stream party</span> platform</p>
        </div>
        <div class="content-btn">
          <button class="btn-register">Create account</button>
          <button class="btn-login" @click="login()">Sign in</button>
        </div>        
      </div>
      <div class="center-panel">
        <div class="header">
          <h4>Fortnite New Season</h4>
          <p>Join Live Stream</p>
        </div>
        <div class="time-user">
          <div class="user">
            <i class="fa fa-user-plus icon" v-if="imgUserAdd == ''"></i>
            <img :src="imgUserAdd" class="avatar" v-else/>
          </div>
          <div class="time" align="center">
            <span>{{time}}</span>
          </div>
        </div>
        <div class="galery" align="center" v-if="theme === 'dark'">
          <img src="../assets/users/01.png"/>
          <div class="img-1">
            <img src="../assets/users/03.png" style="height: 100%;"/>
          </div>
          <div class="img-2">
            <img src="../assets/users/04.png" style="height: 100%"/>
          </div>                
        </div>
        <div class="galery" align="center" v-else>
          <img src="../assets/users/02.png"/>
          <div class="img-1">
            <img src="../assets/users/03.png" style="height: 100%;"/>
          </div>
          <div class="img-2">
            <img src="../assets/users/01.png" style="height: 100%"/>
          </div>                
        </div>
      </div>
      <div class="right-panel">
        <div class="platform">
          <p class="title">01. <span>Choose Platform</span></p>
          <div class="options-platform">
            <button class="btn-platform active">Party</button>
            <button class="btn-platform">Matchs</button>
            <button class="btn-platform">Streams</button>
          </div>
        </div>
        <div class="search">
          <p class="title">02. <span>Searching Game</span></p>
          <div class="warzone">
            <div class="header">
              <span style="float: left">COD Warzone</span>
              <div class="dropdown" align="end">
                <button class="dropbtn">    
                  <i class="fa fa-sliders"></i>  
                </button>
                <div class="dropdown-content">
                  <p class="title-filter">Filters</p>
                  <div class="items-filters">
                    <p>Gender</p>
                    <input type="checkbox" id="female" name="female" v-model="form.female">
                    <label for="female"> Female</label>
                    <input type="checkbox" id="male" name="male" v-model="form.male">
                    <label for="male"> Male</label>
                  </div>
                  <div class="items-filters">
                    <p>Superpowers</p>
                    <input type="checkbox" id="yes" name="yes" v-model="form.yes">
                    <label for="yes">Yes</label>
                    <input type="checkbox" id="no" name="no" v-model="form.no">
                    <label for="no">No</label>
                  </div>
                  <div class="items-filters">
                    <p>Type</p>
                    <input type="checkbox" id="neutral" name="neutral" v-model="form.neutral">
                    <label for="neutral">Neutral</label>
                    <input type="checkbox" id="hostile" name="hostile" v-model="form.hostile">
                    <label for="hostile">Hostile</label>
                  </div>
                </div>
              </div> 
            </div>
            <div class="list-search">
              <div class="item-list" v-for="(item, index) in listUsers" :key="index">
                <div class="number-item">
                  <span>{{ index+1 }}</span>
                </div>
                <div class="name-item">
                  <span>{{item.name}}</span>
                </div>  
                <div class="avatars">
                  <img :src="item.avatars[0]" class="avatar-1">
                  <img :src="item.avatars[1]" class="avatar-2">
                </div>
               <div align="end">
                  <button class="btn-item" @click="addUser(item)">+</button>
                </div>                   
              </div>
            </div>
            <div class="btn-search">
              <button @click="search()">Search Now</button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'MainSection',  
  props: {
    theme: String
  },
  data (){
    return {
      time: '',
      users:[
        {
          name: 'Lexa',
          gender: 'female',
          superpowers: 'yes',
          type:'neutral',
          avatars: ['/img/avatars/1_01.jpg', '/img/avatars/1_02.jpg']
        },
        {
          name: 'El Mandaloriano',
          gender: 'male',
          superpowers: 'no',
          type:'hostile',
          avatars: ['/img/avatars/2_01.jpg', '/img/avatars/2_02.jpg']
        },
        {
          name: 'Jaleo',
          gender: 'male',
          superpowers: 'no',
          type:'hostile',
          avatars: ['/img/avatars/3_01.jpg', '/img/avatars/3_02.jpg']
        },
        {
          name: 'Depredador',
          gender: 'male',
          superpowers: 'yes',
          type:'hostile',
          avatars: ['/img/avatars/4_01.jpg', '/img/avatars/4_02.jpg']
        },
        {
          name: 'Reese',
          gender: 'female',
          superpowers: 'no',
          type:'neutral',
          avatars: ['/img/avatars/5_01.jpg', '/img/avatars/5_02.jpg']
        },
        {
          name: 'Girasol',
          gender: 'female',
          superpowers: 'no',
          type:'neutral',
          avatars: ['/img/avatars/6_01.jpg', '/img/avatars/6_02.jpg']
        }
      ],
      form:{
        female: false,
        male: false,
        yes: false,
        no: false,
        hostile: false,
        neutral: false
      },
      listUsers: [],
      imgUserAdd: ''
    }
  },
  created () {
    setInterval(this.getNow, 1000)
    this.listUsers = this.users
    console.log('main section', this.theme)
  },
  methods: {
    getNow() {
      const today = new Date();
      this.time = today.getHours() + ":" + (today.getMinutes() < 10 ? '0'+today.getMinutes() : today.getMinutes());      
    },
    search(){
      let temp = []
      if(this.form.female){
        temp = this.users.filter(x=>x.gender == 'female')       
      }
      if(this.form.male){
        temp = temp.concat(this.users.filter(x=>x.gender == 'male'))        
      }
      if(this.form.yes){
        temp = temp.concat(this.users.filter(x=>x.superpowers == 'yes'))        
      }
      if(this.form.no){
        temp = temp.concat(this.users.filter(x=>x.superpowers == 'no'))        
      }
      if(this.form.neutral){
        temp = temp.concat(this.users.filter(x=>x.type == 'neutral'))        
      }
      if(this.form.hostile){
        temp = temp.concat(this.users.filter(x=>x.type == 'hostile'))        
      }
      this.listUsers = [...new Set(temp)];
    },
    addUser(item){
      this.imgUserAdd = item.avatars[0] !== this.imgUserAdd ? item.avatars[0] : item.avatars[1]
    },
    login(){
      this.$router.push({ 
        name: 'login',
      })
    }
  }
}
</script>
