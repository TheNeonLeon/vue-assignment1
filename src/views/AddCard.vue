<template>
  <div>
    <Top  h1="ADD A NEW BANK CARD" h5="NEW CARD"/>
    <Card v-bind:card="card"/>
    <CardForm v-on:updateCard="updateCard"/>
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
    updateCard(input) {
      this.card = input;
    }
  }
}
</script>

<style scoped>
  .add-card {
    position: absolute;
    height: 72px;
    left: 16px;
    top: 808px;
    padding: 5%;
    background: #000000;
    border-radius: 10%;
    color: #FFFFFF;
    cursor: pointer;
  }
  .home-btn{
    position: absolute;
    height: 72px;
    left: 150px;
    top: 808px;
    padding: 5%;
    color: #FFFFFF;
    background: #000000;
    border-radius: 10%; 
    cursor: pointer;
  }
</style>