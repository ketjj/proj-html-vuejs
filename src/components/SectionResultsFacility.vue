<template>
  <div class="total text-center">
    <!-- TESTIMONIALS -->

    <div id="testimonials" class="k_container">
      <div id="title">
        <div class="section-title">Real world result</div>
        <img src="../assets/img/divider-xx-red.png" alt="">
      </div>

      <div class="results row row-cols-1 row-cols-md-2">
        <div v-for="(feedback,index) in FeedbackList" :key="`feed-${index}`" class="result-wrap col">
          <div>
            <img :src="require(`../assets/img/${feedback.image}`)" :alt="feedback.title">
            <p><em>"{{feedback.message}}"</em></p>
            <p class="author">- {{feedback.author}}</p>
          </div>
        </div>
      </div>      
    </div>

    <!-- FACILITIESd -->
    <div id="facilities" class="k_container">
      <div id="title">
        <div class="section-title">Hight performance facilities</div>
        <img src="../assets/img/divider-xx-red.png" alt="">
      </div>
      <div class="results lower row row-cols-2 row-cols-md-3" id="lower-sec">
        <div v-for="(facility,index) in FacilitiesList" :key="`facility-${index}`" class="col image-f">
          <img :src="require(`../assets/img/${facility.image}`)" :alt="facility.id">
        </div>
      </div>         
    </div>
    <!-- //FACILITIESd -->

    <div class="motivate-banner">
      <div class="overlay"></div>

    </div>

  </div>
</template>

<script>
import FeedbackList from '@/data/FeedbackList'
import FacilitiesList from '@/data/FacilitiesList'

export default {
 name: 'SectionResultsFacility',
 data(){
   return{
    FeedbackList: FeedbackList,
    FacilitiesList: FacilitiesList
   }
 }
}
</script>

<style lang="scss" scoped>
 @import '../assets/style/vars';


 #testimonials{
   margin-bottom: 180px;
 }

.total{
  //min-height:800px;
  background-color: $primaryShark-color;
  padding-bottom:8em;
  .section-title{
  text-transform: uppercase;
  font-size: 24px;
  font-weight:600;
  word-spacing: 5px;
  padding-top: 4em;
  
  }
  #title {
    padding-bottom: 40px;
    img{
     margin: 30px 0;
     width: 30px;
    }
  }
  .results{
    min-height: 420px;
    .result-wrap{
      padding:20px;
      display: flex;
      div{
        width:100%;
        height: 100%;
        background-color: $secondaryShark-color;
        padding: 20px;
        img{
        height: 100%;
        float:left;
        margin-right: 20px;
        }
        p{
          text-align: left;
          font-size: 12px;
          text-transform: italic;
          color: $edward-light;
          margin-bottom: 5px;
        }
        .author{
          text-align: left;
          font-weight: 14px;
          font-weight: 700;
          color:white;
        }
      }
    }
  }
  .image-f{
    //height: 300px;
    margin-bottom: 30px;
    img{
    width:100%;

    }
  }
  #lower-sec{
    margin-bottom: 8em;
  }
}
.motivate-banner{
  width:100%;
  height:500px;
  background-image: url('../assets/img/home-testimonial-bg.jpg');
  background-position: center;
  background-size: cover;
  background-attachment: local;
  opacity: .8;
}

</style>