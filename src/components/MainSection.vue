<template>
  <div class="main-section">
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
          <button class="btn-login">Sign in</button>
        </div>        
      </div>
      <div class="center-panel">
        <div class="header">
          <h4>Fortnite New Season</h4>
          <p>Join Live Stream</p>
        </div>
        <div class="time-user">
          <div class="user">
            <span>UU</span>
          </div>
          <div class="time" align="center">
            <span>9:40</span>
          </div>
        </div>
        <div class="galery" align="center">
          <img src="../assets/users/01.png"/>
          <div class="img-1">
            <img src="../assets/users/03.png" style="height: 100%;"/>
          </div>
          <div class="img-2">
            <img src="../assets/users/04.png" style="height: 100%"/>
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
              <span>COD Warzone</span>
            </div>
            <div class="list-search">
              <div class="item-list">
                <div class="number-item">
                  <span>1</span>
                </div>
                <div class="name-item">
                  <span>Dr Team</span>
                </div>                          
                <button class="btn-item">+</button>
              </div>
            </div>
            <div class="btn-search">
              <button>Search Now</button>
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
}
</script>
