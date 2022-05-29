<template>
  <div class="trainers">
    <div class="k_container text-center">
      <div id="title">
        <div class="section-title">Meet our trainers</div>
        <img src="../assets/img/divider-xx-red.png" alt="">
      </div>

      <div class="trainers-section">
        <div v-for="(trainer,index) in TrainersList" :key="`tr-${index}`" class="trainer-card">
          <div class="image">
             <img :src="require(`../assets/img/${trainer.image}`)" :alt="trainer.name">
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
          <div v-for="(trainer,index) in moreTrainers" :key="`alltrainers-${index}`" class="trainer-card">
          <div class="image">
             <img :src="require(`../assets/img/${trainer.image}`)" :alt="trainer.name">
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
        </div>
      </div>

      <div @click="isVisible = !isVisible" class="button">
        <ButtonCompCopy/>
      </div>
    </div>
  </div>
</template>

<script>
import SocialIcons from '@/components/SocialIcons'
import ButtonCompCopy from '@/components/ButtonCompCopy'
import TrainersList from '@/data/TrainersList'

export default {
 name: 'SectionTrainers',
 components:{
   SocialIcons,
   ButtonCompCopy
 },
 data(){
  return{
  TrainersList: TrainersList,
  isVisible: false,

  moreTrainers:[
      {
        image: 'trainer-photo4.webp',
        id: '4',
        name: 'Bruce Johnson',
        position: 'Personal Trainer',
        about: ' I am a certified Personal Trainer who is extremely passionate about fitness and    health'
        },
      {
        image: 'trainer-photo5.webp',
        id: '5',
        name: 'Derek Lee',
        position: 'Coach',
        about: 'My name is Javon Woods and Im a certified TEAM USA boxing coach andownerof a    certification with the National Academy of Sports Medicine'
      },
      {
        image: 'trainer-photo6.webp',
        id: '6',
        name: 'Sasha Smith',
        position: 'Coach',
        about: 'With 10 years of experience I know what it takes to help clients of all shapes and    sizes.'
      },
     ]
   }
 }
}
</script>

<style lang="scss" scoped>
 @import '../assets/style/vars';

 .trainers{
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
    margin-bottom: 20px;

    .trainer-card{
      width: 32%;
      //min-height: 550px;
      overflow: hidden;
      position: relative;
      cursor: pointer;
      text-align: center;
      margin-bottom:30px;
      .image{
        height: 215px;
        &:hover ~.hidden-part{
          height:320px;
          cursor:pointer;
          transition: all 1s ease;
        }
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
        height: 0;
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
 }

</style>