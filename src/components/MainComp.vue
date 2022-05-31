<template>
  <div class="main">

    <div class="upper">
      <div class="k_container text-center container-fluid">

        <!-- INSERIRE IL SECTION TITLE -->
        <div id="title">
          <div class="section-title">World  class  fitness</div>
          <img src="../assets/img/divider-xx-red.png" alt="">
        </div>
        <p>At Avada Gym, everything we do from top to bottom is the hightest quality to ensure we're equipped <br> to help you to reach your goals of a healthy and fit lifestyle.</p>
      </div>

      <img src="../assets/img/background-line.png" alt="background-line">

    </div>

    <div class="lower">
      <div class="k_container text-center container-fluid">
        <div class="row">

          <!-- IMAGE SIDE -->

          <div class="col-12 col-md-6 col-image">
            <img src="../assets/img/home_img-compressor-400x222.jpg" alt="">
          </div>

          <!-- FORM SIDE -->
          <div class="col-12 col-md-6 submit">
            <SignUpComp/>
          </div>         
        </div>     
      </div>
    </div>
  
      <!-- SECTION BENEFITS -->
    <SectionBenefits/>
    
      <!-- SECTION RESULTS AND FACILITIES -->

    <SectionResultsFacility/>

    <!-- SECTION TRAINERS -->

    <SectionTrainers/>

    <!-- SECTION ARTICLES -->
    <SectionArticles/>


  </div>
</template>

<script>
import SignUpComp from '../components/SignUpComp'
import SectionBenefits from '../components/SectionBenefits'
import SectionResultsFacility from '../components/SectionResultsFacility'
import SectionTrainers from '../components/SectionTrainers'
import SectionArticles from '../components/SectionArticles'


export default {
 name: 'MainComp',
 components:{  
   SignUpComp,
   SectionBenefits,
   SectionResultsFacility,
   SectionTrainers,
   SectionArticles,
   
  }
}
</script>

<style lang="scss" scoped>
@import '../assets/style/vars';


// UPPER
.upper{
  min-height:300px;
  background-color: $primaryShark-color;
  .section-title{
  text-transform: uppercase;
  font-size: 24px;
  font-weight:600;
  word-spacing: 5px;
  padding-top: 4em;
  }
  #title img{
   margin: 30px 0;
   width: 30px;
  }
  img{
    width: 100%;
    background-color: $secondaryShark-color;
  }
  p{
    color:$edward-light;
    line-height: 30px;
    margin-bottom: 30px;
  }
}

// LOWER
.lower{
  min-height:520px;
  background-color: $secondaryShark-color;
  padding: 90px 0 50px 0;
  .col-image{
    padding:15px;
    img{
      width:100%;
    }
  }

}

</style>