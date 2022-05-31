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
  width:calc((100% / 3) - 30px);
  margin-bottom:30px;
  margin: 15px;
  img{
    width:100%;
     max-height:300px;
     object-fit: cover;
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

@media (max-width: 768px) {
  .card-article{
    width: 200px;
   }
  .text{
    display:none;
  }
  img{
    height:150px;
  }
}


    
</style>