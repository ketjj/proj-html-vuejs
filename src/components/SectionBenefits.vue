<template>
  <div id="benefits">
    <div class="k_container container-fluid">
      <div class="row row-cols-sm-2 row-cols-lg-4">
        
        <div v-for="(benefit,index) in BenefitsList" :key="index" class="col text-center">
          <i :class="`fa-solid ${benefit.icon}`"></i> 
          <h6>{{benefit.title}}</h6>
          <img src="../assets/img/divider-x-red.png" :alt="benefit.title">
          <p>{{benefit.description}}</p>
        </div>
      </div>      
    </div>

  </div>
</template>

<script>
import BenefitsList from '@/data/BenefitsList'

export default {
  name: 'SectionBenefits',

  data(){
    return{
      BenefitsList: BenefitsList
    }
  }
}
</script>

<style lang="scss" scoped>
@import '../assets/style/vars';


#benefits{
  min-height: 550px;
  background-image: url('../assets/img/gym_bkgd_bw-compressor.jpg');
  background-position: top;
  background-size: cover;
  display: flex;
  align-items: center;
}
  .k_container{
    .col{
      max-height: 300px;
      margin: 40px 0;
    }
  .fa-solid{
    font-size: 30px;
    display: inline-block;
    padding: 15px;
    color: $chestNut-lighterred;
    border: 2px solid $chestNut-darkred;
    border-radius: 50%;
  }
  h6{
    font-weight: 600;
    margin: 18px 0;
  }
  p{
    font-size:14px;
    color: $edward-light;
    line-height: 25px;
    max-height:200px;
    overflow: auto;
  }
  }


</style>