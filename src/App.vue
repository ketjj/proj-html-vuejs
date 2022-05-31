<template>
  <div v-cloak>
    <HeaderComp/>
    <MainComp/>
    <FooterComp/>


    <div id="pagetop" v-show="scY > 300" @click="toTop"><i class="fa-solid fa-arrow-up"></i>
    </div>

  </div>
</template>

<script>
import HeaderComp from './components/HeaderComp.vue'
import MainComp from './components/MainComp.vue'
import FooterComp from './components/FooterComp.vue'

export default {
  name: 'App',
  components: {
    HeaderComp,
    MainComp,
    FooterComp
  },
  data() {
    return {
      scTimer: 0,
      scY: 0,
    }
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll)
  },
  methods:{
    handleScroll: function () {
      if (this.scTimer) return;
      this.scTimer = setTimeout(() => {
      this.scY = window.scrollY;

      clearTimeout(this.scTimer);
      this.scTimer = 0;
      }, 100);
    },

    toTop: function () {
    window.scrollTo({
      top: 0,
      behavior: "smooth"
    });
    },
 }
}
</script>

<style lang="scss">

@import './assets/style/general';
@import './assets/style/vars';

#pagetop{
  position: fixed;
  z-index: 995;
  bottom: 40px;
  right:50px;

}

.fa-arrow-up{
  color:black;
  padding: 12px 15px;
  background-color: $oslo-gray;
  border-radius: 50%;
  &:hover{
    background-color:white;
    cursor: pointer;
    color:$chestNut-lighterred;
  }
}

</style>
