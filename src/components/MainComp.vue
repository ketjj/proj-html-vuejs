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
        <div class="input-section row row-cols-2">
          <div class="col">
            <img src="../assets/img/home_img-compressor-400x222.jpg" alt="">
          </div>

          <div class="input-section col">
            <h5>Sing Up For A Free Training Sessions</h5>
           
              <form>
                <div class="k_form">
                  <label for="exampleInputPassword1">Name:</label>
                    <input type="text" class="form-control" id="exampleInputPassword1" placeholder="Name">
                </div>


                <div class="k_form text-left">
                  <label for="exampleInputEmail1">Email </label>
                    <input type="email" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp" placeholder="Enter email">
                    <!-- <small id="emailHelp" class="form-text text-muted">We'll never share your email with anyone else.</small> -->
                </div>

                <button type="submit" class="btn btn-primary k_button">Start now!</button>

              </form>
          </div>
        </div>     
      </div>
    </div>
  </div>
</template>

<script>
import SectionTitle from '@/components/SectionTitle'
export default {
 name: 'MainComp',
 components:{ SectionTitle }
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
  .input-section div{
    float:left;
    clear:both;
    h5{
      float:left;
      margin-bottom:10px;
    }
  }
  label{
    float:left;
    margin-bottom: 5px;
    color: $edward-light;
  }
  input{
    margin-bottom:20px;
    border-radius: 0;
    background-color:$secondaryShark-color;
    border: .5px solid $doveGray-dark;
    color: white;
  }
  .k_form{
    width: 425px;
  }
  .k_button{
    width:98%;
    float:left;
    text-transform:uppercase;
    margin-top: 15px;
    background-color:$chestNut-darkred;
    border-color:$chestNut-darkred;
    padding: 10px 0;
  }

}

</style>