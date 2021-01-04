<template>
  <div>
    <Top  h1="ADD A NEW BANK CARD" h5="NEW CARD"/>
    <Card v-bind:card="card"/>
    <CardForm v-on:changeCard="changeCard"/>
    <div>
      <button class="add-card" @click="addCard">ADD CARD</button>
      <button class="home-btn" @click="home"> HOME</button>
    </div>
  </div>
</template>

<script>
import Top from "../components/Top";
import Card from "../components/Card";
import CardForm from "../components/CardForm";
export default {
  name: "AddCards",
  components: {
    Top,
    Card,
    CardForm
  },
  data: () => {
    return {
      card: {},
      cards: []
    };
  },
  methods: {
    home() {
      this.$router.push('/')
    },
    addCard () {
        this.$emit('card', this.card);
        this.$router.push("/");
    },
    changeCard(input) {
      this.card = input;
    }
  }
}
</script>

<style scoped>
  .add-card {
    position: absolute;
    height: 72px;
    left: 400px;
    top: 900px;
    padding: 2%;
    padding-left: 5%;
    padding-right: 5%;
    background: #000000;
    border-radius: 5%;
    color: #FFFFFF;
    cursor: pointer;
  }
  .home-btn{
    position: absolute;
    height: 72px;
    left: 700px;
    top: 900px;
    padding: 2%;
        padding-left: 5%;
    padding-right: 5%;
    color: #FFFFFF;
    background: #000000;
    border-radius: 5%; 
    cursor: pointer;
  }
</style>