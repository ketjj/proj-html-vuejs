<template>
<div>
  <div class="header">
    <div class="logo">
     <img src="../assets/img/gym_logo_1x.png" alt="">
    </div>

    <div class="nav">

        <ul>
          <li v-for="(navlink,index) in NavLinkList" :key="index"><a :href="navlink.id" :class="{'active': navlink.isSelected}">{{navlink.name}}</a></li>
        </ul>
        <!-- HAMBURGER MENU STARTS HERE-->

    </div>
    <div class="hamburger" @click="isShown = !isShown">
         <span class="bar"></span>
         <span class="bar"></span>
         <span class="bar"></span>

    </div>
  </div>
    <ul v-if="isShown" class="hamburger-menu" :class="{'open' : isShown}">
      <li v-for="(navlink,index) in NavLinkList" :key="index"><a :href="navlink.id" :class="{'active': navlink.isSelected}">{{navlink.name}}</a></li>
    </ul>


    


  <div class="jumbo">
    <!-- <img src="../assets/img/home-banner.jpg" alt=""> -->
    <div class="k_container text-center">
    <div class="banner-text pb-2">No pain no gain</div>
    <h6>Motivation is what gets you started. Habit is what keeps you going</h6>
    <div class="text-center">
      <ButtonComp buttonText="Join us today!"/>
      
    </div>
    </div>
  </div>


</div>
  
</template>

<script>
import NavLinkList from '../data/NavLinkList';
import ButtonComp from '../components/ButtonComp'


export default {
 name: 'HeaderComp',
 components:{ ButtonComp },
 data(){
   return{
     NavLinkList: NavLinkList,
     isShown: false
   }
 }
}
</script>

<style lang="scss" scoped>
@import '../assets/style/HeaderStyle';
@import '../assets/style/vars';


.jumbo{
  width:100%;
  height: 200px;
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 720px;
  background-image: url('../assets/img/home-banner.jpg');
  background-position: center;
  background-size: cover;
  background-attachment: fixed;
  .k_container{
    height:210px;
  }
  
}
.banner-text{
 font-size: 5em;
 font-weight: 700;
 text-transform: uppercase;
}
h6{
  color: lighten($edward-light, 10%);
  margin-bottom: 40px;
  font-family: 'Saira', sans-serif;
  word-spacing: 2px;
}
li.active{
  background-color: $oslo-gray;
   color:black;
}

</style>