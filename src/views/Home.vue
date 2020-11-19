<template>
  <div class="home">
   <!-- <img alt="Vue logo" src="../assets/logo.png">-->
  <div class="container">
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
  </div>
  <router-link to="/addcard">
    <button @click="addCard" class="add-card">
      ADD NEW CARD
  </button>
  </router-link>
  </div>
</template>

<script>
import Card from '../components/Card'
/* import CardStack from '../components/CardStack'
import Top from '../components/Top' */
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  components: {
    Card
  },
  props: {
    CardStack: Object
  },
  data: () => {
    return {
      Card: []
    }
  },
  methods: {
    changeCard (card) {
      this.Card
    }
  }
}
</script>
<style scoped>
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
