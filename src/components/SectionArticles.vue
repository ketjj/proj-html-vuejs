<template>
  <div id="articles">
    <div class="k_container">
      <div id="title">
        <div class="section-title">Meet our trainers</div>
        <img src="../assets/img/divider-xx-red.png" alt="">
      </div>

      <div class="main-articles">
        <CardArticles 
        v-for="(article,index) in articles" :key="`art-${index}`"
        :articleOb="article"/>
      </div>

      <div v-if="isVisible" class="main-articles">
        <CardArticles 
        v-for="(article,index) in PerformanceNewsList" :key="`per-${index}`"
        :articleOb="article"/>
      </div>

      <div @click="isVisible = !isVisible" class="button">
        <ButtonCompArticle/>
      </div>

    </div>
  </div>
</template>

<script>
import CardArticles from '@/components/CardArticles'
import PerformanceNewsList from '@/data/PerformanceNewsList'
import ButtonCompArticle from '@/components/ButtonCompArticle'

export default {
 name: 'SectionArticles',
 components:{
   CardArticles,
   ButtonCompArticle
 },
 data(){
   return{
    PerformanceNewsList: PerformanceNewsList,
    isVisible: false,
    articles: [
      {
      image: 'blog1.jpg',
      title: 'Train with free weights or your body weight?',
      article: 'Calisthenics uses your bodyweight and involves compound exercises. It requires a lot of movement and a lot of hard working also a streight mental health [...]'
      },
      {
      image: 'blog4.jpg',
      title: 'To be number one, train like you\'re number two',
      article: 'He wrote that the quote «To be number one, you must train like you are number two» was Maurice Green [...]'
      },
      {
      image: 'blog6.jpg',
      title: 'Nutritional advice that will keep you training',
      article: 'Eat a healthy breakfast. If you exercise in the morning, get up early enough to finish breakfast [...]'
      },
      {
      image: 'trainer3-400x297.jpg',
      title: 'Top 5 mistakes every gym member makes',
      article: 'The most common mistakes that gym owners make:Not Having Enough Options and Spending Too Much Time on Training [...]'
      },
      {
      image: 'trainer4-400x297.jpg',
      title: 'Simple principles for your next workout',
      article: 'If you have the option, utilize a free personal training session at your gym to have a trainer give you one-on-one attention for perfecting your form [...]'
      },
      {
      image: 'trainer1-400x297.jpg',
      title: 'The myths of shedding body fat explored',
      article: 'Team up with a coworker to work out before the workday starts, make friends with people at your gym [...]'
      }
    ]
   }
 }
 
}
</script>

<style lang="scss" scoped>
 @import '../assets/style/vars';

#articles{
  background-color: $primaryShark-color;
  min-height:1200px;
  #title {
    padding-bottom: 40px;
    text-align: center;
    .section-title{
    text-transform: uppercase;
    font-size: 24px;
    font-weight:600;
    word-spacing: 5px;
    padding-top: 8em;
    }
    img{
     margin: 30px 0;
     width: 30px;
    }
  }
  .main-articles{
    width:100%;
    max-height: 1000px;
    margin-bottom:100px;
    display: flex;
    flex-direction: column;
    flex-wrap:wrap;
    justify-content: space-between;
  }
  .button{
    text-align:center;
    margin:0 auto;
  }
 }
</style>