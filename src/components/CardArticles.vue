<template>

  <div class="card-article">
    <img :src="require(`../assets/img/${articleOb.image}`)" alt="article">
    <div class="text">
      <div class="title">{{articleOb.title}}</div>
      <p>{{articleOb.article}}</p>
    </div>
  </div>

</template>

<script>
export default {
 name: 'CardArticles',
 props:{
   articleOb:Object
 }
}
</script>

<style lang="scss" scoped>
 @import '../assets/style/vars';

.card-article{
    background-color: $secondaryShark-color;
    width:31%;
    margin-bottom:30px;
    img{
      width:100%;
       max-height:300px;
    }
    .text{
      width:100%;
      padding:20px 20px 0 20px;
      //text-align: justify;
      .title{
       font-weight: 600;
       margin:0;
      }
      p{
        font-size: 14px;
        color:$doveGray-dark;
        margin-top:5px;
        line-height:25px;
      }
    }
    }
</style>