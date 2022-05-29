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


    <!-- BANNER -->

    <div class="motivate-banner">
      <div class="overlay">
        <div class="k_container">
          <h3>" I fear not the man who has practiced 10,00 <br> kicks once, but I fear the man who has <br> practiced one kick 10,000 times "</h3>
          <img src="../assets/img/divider-white-xx.png" alt="">
          <div class="author">bruce lee - Quote of the day
            </div>
        </div>
      </div>

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
    &:hover{
      transform: scale(1.5);
      transform: translate(0, 20px);
    }
    img{
    width:100%;

    }
  }
  #lower-sec{
    margin-bottom: 8em;
    img{
      &:hover{
        filter: brightness(200%);
        cursor: pointer;
        transition: all .5s ease-in-out;
      }

    }
  }
}
.motivate-banner{
  position: relative;
  width:100%;
  height:500px;
  background-image: url('../assets/img/home-testimonial-bg.jpg');
  background-position: center;
  background-size: cover;
  background-attachment: local;
  //opacity: .8;
  .overlay{
    position: absolute;
    top:0;
    left:0;
    width:100%;
    height:100%;
    background-color: rgba($color: #000000, $alpha: .1);
    &:hover{
      background-color: rgba($color: #000000, $alpha: .4);
      transition: all 2s ease;
    }
    h3{
      margin-top:120px;
      word-spacing: 2px;
      line-height: 40px;
    }
    img{
      margin-top: 30px;
      margin-bottom: 50px;
    }
    .author{
      text-transform: uppercase;
      font-size: 14px;
      font-weight: 500;
    }
    i{
      font-size: 5px;
      line-height: 14px;
    }
    }
}

</style>