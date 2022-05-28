<template>
<div>
  <div v-if="visible" class="input-section">
    <p>Sing Up For A Free Training Sessions!</p> 
           
      <div class="subscription" > <!--  @submit.prevent="handleSubmit()"> -->
      <!-- uso una semplice div, e faccio i contolli manuali -->
        <div class="k_form">
          <label>Name: <i class="fa-solid fa-asterisk"></i></label>
          <input type="text" class="form-control" placeholder="Name" required
          v-model.trim="insertName">

          <div class="n-error">{{nameMessageError}}</div>
        </div>

        <div class="k_form text-left">
          <label>Email: <i class="fa-solid fa-asterisk"></i></label>
          <input type="email" required class="form-control" placeholder="Enter email" 
          v-model.trim="insertMail" >

          <div class="n-error">{{mailMessageError}}</div>

        </div>

        <button type="submit" @click="handleSubmit()" class="btn btn-primary k_button">Start now!</button>

        <!-- @click="handleSubmit()" @keyup.enter="makeSubscription" -->

      </div>
  </div>
  <div v-else class="sub-success">{{successMessage}}</div>

</div>

</template>

<script>
export default {
  name: 'SignUpComp',

   data(){
    return{
     insertMail: '',
     insertName: '',
     nameMessageError: '',
     mailMessageError: '',
     successMessage:'',
     visible: true
    }
   },
  methods: {

    handleSubmit(){

       this.nameMessageError = ( /^(?!-)[a-zA-Z-]*[a-zA-Z]$/.test(this.insertName) && this.insertName.length > 2) ? '':'Name must be at least 3 letters, no numbers and special characters';

       //per contollare la mail inserito uso una forma di Regex...Che con Vue va in una specie di conflitto con " \. "  , e ho dovuto disabilitare i controlli sulla  prossima linea successiva --->

       //eslint-disable-next-line
       this.mailMessageError = (/^\w+([\.-]?\w+)*@\w+([\.-]?\w+)*(\.\w{2,3})+$/.test(this.insertMail)) ? '': 'Please provide a correct email address!';

      if( this.mailMessageError == '' && this.nameMessageError == '' )
      {
           this.successMessage = 'Congrats, you\'re one of us!';
           this.insertMail = '';
           this.insertName = '';
           this.visible = false;
      }
      else{
        this.successMessage = 'Please repeat!';
      }
    }
  }
}
</script>

<style lang="scss" scoped>
@import '../assets/style/vars';

.input-section{
  flex-basis:50%;
  min-height: 300px;
  justify-content: start;
  text-align: left;
  padding:15px;
  outline: 0;
  box-shadow: 0 0 0 1px $secondaryShark-color;
  col{
    flex-basis: 50%;
    padding:10px;
  }
  .n-error{
    color:red;
    font-size: 12px;
    margin-bottom:10px;
  }
  p{
    font-size:18px;
    font-weight: 600;
    word-spacing: 2px;
    margin-bottom:10px;
  }
  label{
    margin-top:10px;
    float:left;
    margin-bottom: 5px;
    color: $edward-light;
  }
  input{
    margin-bottom:10px;
    border-radius: 0;
    background-color:$secondaryShark-color;
    border: .5px solid $doveGray-dark;
    color: white;
    
    &:focus{
      background-color: rgba($chestNut-darkred, 20%);
      border-color:$chestNut-darkred;
      color: white;
      box-shadow:none;
    }
  }
  .fa-asterisk{
    font-size:20px;
    font-family:none;
    color:$chestNut-darkred;
  }
  .k_button{
    width:100%;
    float:left;
    text-transform:uppercase;
    margin-top: 15px;
    background-color:$chestNut-darkred;
    border-color:$chestNut-darkred;
    padding: 10px 0;
  }

}
  .sub-success{
    font-size: 24px;
    color: lighten($yellow, 60%);
    font-weight: 600;
    text-transform: uppercase;
    padding-top: 6rem;
  }

</style>