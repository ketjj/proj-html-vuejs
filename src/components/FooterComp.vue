<template>
  <div class="footer">
    <!-- SMALL BANNER -->
    <div class="small-banner d-flex align-items-center">
      <div class="k_container row">
        <div class="col-12 col-md-6 col-lg-8">
          <h3>Achieve Your Fitness Goals</h3>
          <div class="under-t">Flexible packages to suit all levels of athletes and achieve your fitness goals.</div>
        </div>

        <div class="col-12 col-md-6 col-lg-4 text-center">
          <ButtonComp :light="true" buttonText="join us"/>
        </div>
      </div>
    </div>
      <!-- //SMALL BANNER -->


    <div class="k_container lower-footer">
      <div class="row row-cols-1 row-cols-sm-2 row-cols-lg-4">
        <div class="col">
          <div class="title">Come find us</div>
          <ul>
            <li>12345 North Main Street</li>
            <li>New York, NY 55555</li>
            <li>Phone: 1.800.555.6789</li>
            <li>Email: info@your-domain.com</li>
          </ul>
        </div>

        <div class="col posts">
          <div class="title">Recent Posts</div>
          <ul>
            <li><i class="fa-solid fa-chevron-right"></i>Train with free weights or your body weight?</li>
            <li><i class="fa-solid fa-chevron-right"></i>Nutritional advice that will keep you training</li>
          </ul>
        </div>

        
        <div class="col opening">
          <div class="title">Opening Times</div>
          <ul>
            <li>
              <div class="days">Weekdays Monday - Friday</div>
              <div class="hours">09:00 - 19:00</div>
            </li>
            <li>
              <div>Weekdays Saturday - Sunday</div>
              <div class="hours" >09:00 - 21:00</div>
            </li>
            
          </ul>
        </div>

        
        <div class="col">
          <img src="../assets/img/gym_ad-compressor-200x133.jpg" alt="">
        </div>

      </div>
      </div>
        <div class="underlower-footer">
          <div class="k_container d-flex justify-content-between h-100">
            <div class="copyright align-self-center"><i class='far fa-copyright'></i>Copyright 2012-2020 | Avada Theme By Theme Fusion | All  Rights Reserved | Powered By Wordpress</div>
            <div class=" align-self-center"> <SocialIcons :red="true"/></div>
          </div>
        </div>
    </div>


</template> 

<script>
import ButtonComp from '@/components/ButtonComp'
import SocialIcons from '@/components/SocialIcons'

export default {
 name: 'FooterComp',
 components:{
   ButtonComp,
   SocialIcons
 }
}
</script>

<style lang="scss" scoped>
@import '../assets/style/vars';

//SMALL BANNER
.small-banner{
  height: 200px;
  background-image: url('../assets/img/home-parallax.jpg');
  background-position: 10% 15%;
  background-size: cover;
  background-attachment: fixed;
  
  .mot-text{
    flex-basis: 60%;
    align-self: center;
    h3{
      font-weight:600;
    }
    .under-t{
      font-size:14px;
    }
  }   
  .button{
    flex-basis: 40%;
  }
}

//LOWER FOOTER
.footer{
  background-color: $secondaryShark-color;
  //height:600px;
  .lower-footer{
    padding: 50px 0;
  }
}

//UNDER_LOWER
.underlower-footer{
  height: 70px;
  background-color:lighten($woodSmoke-black, 8%) ;
}
.title{
  text-transform: uppercase;
  color: $doveGray-dark;
  font-weight: 500;
  margin-bottom: 20px;
}
ul{
  padding-left: 0;
}
ul li{
  font-size: 14px;
  line-height: 25px;
  color: $edward-light;
}
.posts li{
  width:100%;
  padding-bottom:10px;
  border-bottom: 1px solid darken($doveGray-dark, 10%) ;
 i{
   margin-right: 10px;
 }
}
.posts li:last-child{
  padding-top: 10px;
}

.opening .hours{
  color: darken($doveGray-dark, 10%);
}
.copyright{
  font-size:12px;
  color: $doveGray-dark;
  i{
    margin-right: 10px;
  }
}

</style>