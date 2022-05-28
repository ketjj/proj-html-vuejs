<template>
  <div class="main">

    <!-- UPPER MAIN -->
    <div class="upper">
      <div class="k_container text-center container-fluid">
        <!-- INSERIRE IL SECTION TITLE -->
          <SectionTitle/>

          <p>At Avada Gym, everything we do from top to bottom is the hightest quality to ensure we're equipped <br> to help you to reach your goals of a healthy and fit lifestyle.</p>
  
      </div>
      <img src="../assets/img/background-line.png" alt="background-line">
    </div>

    <div class="lower">
      <div class="k_container text-center container-fluid">

        <div class="d-flex">

          <!-- IMAGE SIDE -->

          <div class="col-image">
            <img src="../assets/img/home_img-compressor-400x222.jpg" alt="">
          </div>

          <!-- FORM SIDE -->
          <div class="submit">
            <SignUpComp/>
          </div>

          
        </div>     
      </div>
    </div>
  </div>
</template>

<script>
import SectionTitle from '@/components/SectionTitle'
import SignUpComp from '@/components/SignUpComp'


export default {
 name: 'MainComp',
 components:{ SectionTitle, SignUpComp },

}
</script>




<style lang="scss" scoped>
@import '../assets/style/vars';

.upper{
  min-height:300px;
  background-color: $primaryShark-color;
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
.lower{
  height:500px;
  background-color: $secondaryShark-color;
  padding: 90px 0 50px 0;
  .col-image{
    flex-basis:50%;
    padding:15px;
    img{
      width:100%;
    }
  }
  .submit{
    flex-basis:50%;
  }
}


</style>