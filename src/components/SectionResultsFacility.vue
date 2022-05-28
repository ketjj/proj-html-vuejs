<template>
  <div class="total text-center">

    <div id="testimonials" class="k_container">
      <div id="title">
        <div class="section-title">Real world result</div>
        <img src="../assets/img/divider-xx-red.png" alt="">
      </div>

      <div>A
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
export default {
 name: 'SectionResultsFacility'
}
</script>

<style lang="scss" scoped>
 @import '../assets/style/vars';

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
}
 

</style>