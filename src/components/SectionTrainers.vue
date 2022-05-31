<template>
  <div id="trainers">
    <div class="k_container text-center">
      <div id="title">
        <div class="section-title">Meet our trainers</div>
        <img src="../assets/img/divider-xx-red.png" alt="">
      </div>

      <div class="trainers-section">
        <div v-for="(trainer,index) in TrainersList" :key="`tr-${index}`" class="trainer-card">
          <div class="image">
             <img onclick="show()" :src="require(`../assets/img/${trainer.image}`)" :alt="trainer.name">
          </div>
          <div class="hidden-part">
            <div class="info d-flex flex-column justify-content-between">
              <div class="name">{{trainer.name}}

              <div>{{trainer.position}}</div>
              </div>
              <p>{{trainer.about}}</p>
              <SocialIcons/>
            
            </div>          
          </div>
        </div>


        <div v-if="isVisible" class="d-flex justify-content-between">
          <div v-for="(trainer,index) in MoreTrainersList" :key="`alltrainers-${index}`" class="trainer-card">
          <div class="image">
             <img :src="require(`../assets/img/${trainer.image}`)" :alt="trainer.name">
          </div>
          <div class="hidden-part">
            <div class="info d-flex flex-column justify-content-between w-100">
              <div class="name">{{trainer.name}}
              <div>{{trainer.position}}</div>
              </div>
              <p>{{trainer.about}}</p>
              <SocialIcons/>            
            </div>          
          </div>
          </div>
        </div>
      </div>

      <div @click="isVisible = !isVisible" class="button">
        <ButtonComp buttonText="View all trainers"/>
      </div>

    </div>
      <img class="line" src="../assets/img/background-linedark.png" alt="">
  </div>
</template>

<script>
import SocialIcons from '@/components/SocialIcons'
import ButtonComp from '@/components/ButtonComp'
import MoreTrainersList from '@/data/MoreTrainersList'

export default {
 name: 'SectionTrainers',
 components:{
   SocialIcons,
   ButtonComp
 },
 methods:{
 
 },

 data(){
  return{
  MoreTrainersList: MoreTrainersList,
  isVisible: false,

  TrainersList:[
  {
    image: 'trainer1-400x297.jpg',
    id: '1',
    name: 'Ann Baker',
    position: 'Personal Trainer',
    about: 'My name is Ann and I am a personal trainer in Avada Gym. AG is a results-based training community committed to helping you achieve your specific fitness goals.'
  },
  {
    image: 'trainer3-400x297.jpg',
    id: '2',
    name: 'Anne Warren',
    position: 'Personal Trainer',
    about: 'We believe everyone should live their life in the body they desire, if they are willing to work for it. So we provide everything you need to do that'
  },
  {
    image: 'trainer4-400x297.jpg',
    id: '3',
    name: 'Peter Rice',
    position: 'Personal Trainer',
    about: 'I am dedicated to constantly improving my life through health and fitness and changing other people\'s lives through health and fitness.'
  },
     ]
   }
 }
}
</script>

<style lang="scss" scoped>
 @import '../assets/style/vars';

 #trainers{
    background-color: $secondaryShark-color;
    min-height:980px;
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
  .trainers-section{
    display:flex;
    flex-wrap: wrap;
    justify-content: space-between;
    transition: all 1s;
    margin-bottom: 100px;

    .trainer-card{
      width: 32%;
      //min-height: 550px;
      overflow: hidden;
      position: relative;
      cursor: pointer;
      text-align: center;
      margin-bottom:30px;
      &:hover{
        animation: shake 1s;}
        box-shadow: 0 0 20px #141414;
        cursor: crosshair;
      .image{
        height: 215px;
        // &:hover ~.hidden-part{
        //   height:320px;
        //   cursor:pointer;
        //   transition: all 1s ease;
        // }
        img{
        position: absolute;
        top: 100px;
        left: 50%;
        transform: translate(-50%, -50%);
        width:100%;
        height:230px;
        object-fit: cover;
        }
      }
      .hidden-part{
        width: 100%;
        height: 320px;
        text-align:left;
        color: $white;
        background-color: $primaryShark-color;
        overflow: hidden;
        transition: height 0.5s;
        .info{
          padding:30px 20px 20px 20px;
          height:100%;
          .name div{
            margin-top: 5px;
          }
          p{
            color:$edward-light; 
            font-size: 14px;
          }
        }       
      }
      .button{
        text-align:center;
        margin:0 auto;
        
      }
    }
  }
  .line{
    background-color: $primaryShark-color;
    width:100%;
  }
  @keyframes shake {
  0% { transform: translate(1px, 1px) rotate(0deg); }
  10% { transform: translate(-1px, -2px) rotate(-1deg); }
  20% { transform: translate(-3px, 0px) rotate(1deg); }
  30% { transform: translate(3px, 2px) rotate(0deg); }
  40% { transform: translate(1px, -1px) rotate(1deg); }
  50% { transform: translate(-1px, 2px) rotate(-1deg); }
  60% { transform: translate(-3px, 1px) rotate(0deg); }
  70% { transform: translate(3px, 1px) rotate(-1deg); }
  80% { transform: translate(-1px, -1px) rotate(1deg); }
  90% { transform: translate(1px, 2px) rotate(0deg); }
  100% { transform: translate(1px, -2px) rotate(-1deg); }
  }
 }

@media (max-width: 768px) {
  .trainers{
    min-height: 0px;
  }

  .trainer-card{
    height: 300px;
    text-align:center;
  }
  .info{
    justify-content: start;
  }
  .info p,
  .name div{
    display:none;
  }
}

</style>