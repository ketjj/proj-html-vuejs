<template>
  <div class="total text-center">

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


    <div id="facilities" class="k_container">
      <div id="title">
        <div class="section-title">Hight performance facilities</div>
        <img src="../assets/img/divider-xx-red.png" alt="">
      </div>
      <div>B
      </div> 
        
    </div>

  </div>
</template>

<script>
import FeedbackList from '@/data/FeedbackList'

export default {
 name: 'SectionResultsFacility',
 data(){
   return{
    FeedbackList: FeedbackList
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
  min-height:800px;
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
}
 

</style>