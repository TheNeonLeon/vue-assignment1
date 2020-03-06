<template>
  <div class="home">
   <!-- <img alt="Vue logo" src="../assets/logo.png">-->
    <h1>E-WALLET</h1>
    <p>Active card</p>
  <div class="bitcoin" ref="bitcoin" v-bind="changeCard">
    <img class="chip" src="@/assets/chip-dark.svg">
    <img class="bitcoin-logo" src="@/assets/vendor-bitcoin.svg">
    <p class="card-number">1234 5435 4666 0931</p>
    <p class="cardholder">cardholder name</p>
  </div>
  <div class="ninja" ref="ninja" @click="changeCard">
    <p class="card-number"></p>
  </div>
  <div class="block-chain" @click="changeCard">
    <p class="card-number"></p>
  </div>
  <!-- implement this code in evil-corp v-for="variant in cardVariants" :key="variant.variantCard" @click="changeCard"-->
  <div class="evil-corp">
    <p class="card-number">6666 6666 6666 6666</p>
  </div>
  <router-link to="/addcard">
    <button @click="addCard" class="add-card">
      ADD NEW CARD
  </button>
  </router-link>
  </div>
</template>

<script>
/* import Card from '../components/Card'
import CardStack from '../components/CardStack'
import Top from '../components/Top' */
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'

export default {
  components: {},
  name: 'CardStack',
  props: {
    CardStack: Object
  }
  /* data: () => {
    return {
    }
  },
  Variants: [
    {
      variantCard: 'evil-corp'
    },
    {
      variantCard: 'block-chain'
    },
    {
      variantCard: 'ninja'
    }
  ],
  methods: {
    changeCard() {
      this.bitcoin = variantCard
    },
  } */
}
</script>
<style scoped>
*{
  padding: 0;
  box-sizing: border-box;
}
.bitcoin{
  display: flex;
  justify-content: center;
  border-style: solid;
  border-color: orange;
  padding: 5%;
  background-color: #FFAE34;
  border-radius: 8px;
  margin-left: 25%;
  margin-right: 25%;
  padding-bottom: 10%;
  box-shadow: 0px 0px 8px rgba(0, 0, 0, 0.25);
}
.bitcoin-logo{
  position: relative;
  left: 70%;
  bottom: 30px;
}
.chip{
  position: relative;
  right: 10%;
  bottom: 20px;
}
.card-number{
  position: relative;
  top: 60px;
  right: 5%;
  font-size: 29px;
  word-spacing: 20px;
}
.cardholder{
position: absolute;
text-transform: uppercase;
left: 28%;
bottom: 23%;
font-size: 12px;
}
.ninja{
  display: flex;
  justify-content: center;
  border-style: solid;
  border-color: black;
  padding: 5%;
  background-color: black;
  border-radius: 8px;
  margin-left: 25%;
  margin-right: 25%;
  margin-top: 8%;
  padding-bottom: 15%;
  box-shadow: 0px 0px 8px rgba(0, 0, 0, 0.25);
  z-index: -1;
}
.block-chain{
  display: flex;
  justify-content: center;
  border-style: solid;
  border-color: blue;
  padding: 5%;
  background-color: blue;
  border-radius: 8px;
  margin-left: 25%;
  margin-right: 25%;
  margin-top: -15%;
  padding-bottom: 15%;
  box-shadow: 0px 0px 8px rgba(0, 0, 0, 0.25);
  z-index: 1;
}
.evil-corp{
  display: flex;
  justify-content: center;
  border-style: solid;
  border-color: red;
  padding: 5%;
  background-color: red;
  border-radius: 8px;
  margin-left: 25%;
  margin-right: 25%;
  margin-top: -15%;
  padding-bottom: 15%;
  box-shadow: 0px 0px 8px rgba(0, 0, 0, 0.25);
  z-index: 2;
}
/*Hover effects on cards*/
.bitcoin:hover, .evil-corp:hover, .block-chain:hover, .ninja:hover{
transform: translateY(-35px);
transition: all 0.5s ease;
}
.add-card{
  margin-top: 10%;
  border-style: solid;
  border-color: black;
  border-radius: 8px;
  background-color: white;
  padding-top: 2%;
  padding-bottom: 2%;
  padding-right: 10%;
  padding-left: 10%;
}
</style>
