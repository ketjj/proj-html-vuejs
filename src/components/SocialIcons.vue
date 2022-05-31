<template>
  <div class="icons">
    <i :class="[red ? 'red': '']" class="fa-brands fa-facebook-f"></i>
    <i :class="[red ? 'red': '']" class="fa-brands fa-twitter"></i>
    <i :class="[red ? 'red': '']" class="fa-brands fa-instagram"></i>
  </div>
</template>

<script>
export default {
  name:'SocialIcons',
  props:{
    red:{
      type: Boolean,
      default: () => false
    },
  }

}
</script>

<style lang="scss" scoped>
@import '../assets/style/vars';

i{
  padding: 10px 15px;
  background-color: darken($secondaryShark-color, 2%);
  margin: 0 5px;
  border-radius: 5px;
}
.red{
  background-color: $chestNut-lighterred;
  
  &:hover{
    background-color: lighten($chestNut-lighterred, 20%);
    color: $irishCoffee;
    cursor: crosshair;
  }
}

@media (max-width: 768px) {
    
  i{
    padding: 4px 8px;
  }
}
</style>