<template>
<div>
  <div class="header">
    <div class="logo">
     <img src="../assets/img/gym_logo_1x.png" alt="">
    </div>

    <div class="nav">
      <ul>
        <li v-for="(navlin,index) in NavLinkList" :key="index"><a href="#">{{navlin.name}}</a></li>
      </ul>
    </div>
  </div>

  <div class="jumbo">
    <img src="../assets/img/home-banner.jpg" alt="">
  </div>

</div>
  
</template>

<script>
import NavLinkList from '@/data/NavLinkList';


export default {
 name: 'HeaderComp',
 data(){
   return{
     NavLinkList: NavLinkList
   }
 }
}
</script>

<style lang="scss" scoped>
@import '../assets/style/HeaderStyle';

.jumbo img{
  width:100%;
  position: relative;
}




</style>