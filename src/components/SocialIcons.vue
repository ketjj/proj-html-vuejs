<template>
  <div class="icons">
    <i class="fa-brands fa-facebook-f"></i>
    <i class="fa-brands fa-twitter"></i>
    <i class="fa-brands fa-instagram"></i>
  </div>
</template>

<script>
export default {
  name:'SocialIcons'

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

</style>