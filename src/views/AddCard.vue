<template>
  <div class="wrapper">
    <h1>ADD A NEW
      BANK CARD</h1>
    <p>NEW CARD</p>
     <img class="chip" src="@/assets/chip-dark.svg">
      <img class="bitcoin-logo" src="@/assets/vendor-bitcoin.svg">
    <div class="new-card">
      <!--Always use @ as your first value when getting an image, as shown below-->
      <!--<img class="chip" src="@/assets/chip-dark.svg">-->
      <p class="cardholder-name">CARDHOLDER NAME</p>
      <!--change dynamic inputs to be static-->
      <p class="dynamic-number" v-bind="number">{{number}}</p>
    </div>
      <p class="dynamic-name" v-bind="name">{{name}}</p>
    <p class="card-text">CARD NUMBER</p>
    <input class="input-card-number" type="text" v-on:input="number = $event.target.value"
    maxlength="19">
    <br>
      <p class="card-name">CARDHOLDER NAME</p>
    <input class="input-card-number" type="text" placeholder="FIRSTNAME LASTNAME" v-on:input="name = $event.target.value">
    <br>
      <p class="card-text">VALID THRU</p>
    <input class="input-date" type="text">
    <br>
      <p class="card-text">VENDOR</p>
    <input list="vendors" class="card-vendor">
    <datalist id="vendors">
      <option value="bitcoin"></option>
      <option value="ninja-bank"></option>
      <option value="block-chain"></option>
      <option value="evil-corp"></option>
    </datalist>
    <br>
  <router-link to="/">
  <button type="submit" class="add-card">
    ADD CARD
  </button>
  </router-link>
  </div>
</template>

<script>
/* import Card from '../components/Card'
import CardStack from '../components/CardStack'
import Top from '../components/Top' */

export default {
  name: 'AddCard',
  data: () => {
    return {
      number: '',
      name: '',
      expiration: '',
      ccv: '',
      vendor: ''
    }
  },
  watch: {
    number () {
      if (this.vendor === '') {

      }
    }
  }
}
</script>

<style scoped>
.card-vendor{
  border-radius: 5px;
  padding-right: 30%;
  border: 1px solid rgba(0, 0, 0, 0.8);
}
.cardholder-name{
  display: flex;
  justify-content: left;
}
.card-text{
 font-style: normal;
 font-weight: normal;
 font-size: 12px;
 line-height: 13px;
 position: relative;
 right: 18%;
}
.card-ccv{
 font-style: normal;
 font-weight: normal;
 font-size: 12px;
 line-height: 13px;
 position: relative;
 right: 18%;
}
.card-name{
 font-style: normal;
 font-weight: normal;
 font-size: 12px;
 line-height: 13px;
 position: relative;
 right: 16.5%;
}
.input-card-number{
  border-radius: 5px;
  padding-right: 30%;
  border: 1px solid rgba(0, 0, 0, 0.8);
}
.input-date{
  border-radius: 5px;
  padding-right: 2%;
  margin-right: 28%;
  border: 1px solid rgba(0, 0, 0, 0.8);
}
.dynamic-number{
  position: relative;
  top: 100px;
  right: 50%;
  font-size: 29px;
  letter-spacing: 0.03em;
}
.dynamic-name{
  position: relative;
  bottom: 45px;
  right: 20%;
}
.chip{
position: relative;
top: 115px;
right: 20%;
}
.bitcoin-logo{
position: relative;
top: 100px;
left: 20%;
}
.new-card{
  display: flex;
  justify-content: center;
  border-style: solid;
  border-color: grey;
  padding: 5%;
  background-color: grey;
  border-radius: 8px;
  margin-left: 25%;
  margin-right: 25%;
  padding-bottom: 15%;
  box-shadow: 0px 0px 8px rgba(0, 0, 0, 0.25);
}
.add-card{
  margin-top: 10%;
  border-style: solid;
  border-color: black;
  border-radius: 8px;
  background-color: black;
  color: white;
  padding-top: 2%;
  padding-bottom: 2%;
  padding-right: 10%;
  padding-left: 10%;
}
</style>
