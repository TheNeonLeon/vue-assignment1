<template>
  <div>
    <div>
      <top 
        h1="E-WALLET" 
        h5="ACTIVE CARD" />
      <card 
        @allCards="pushCard"
        :card="card"
      />
    </div>
    <div>
      <CardStack 
        v-bind:allCards="cards"
        @pushCard="pushCard"/>
    </div>
    <div>
      <button class="add-new-card-btn" @click="addCard">
        ADD CARD
      </button>
    </div>
  </div>
</template>

<script>
import top from "../components/Top";
import card from "../components/Card";
import CardStack from "../components/CardStack";
export default {
  name: "Cards",
  components: {
    top,
    card,
    CardStack,
  },
  data: () => {
    return {
      card: {}
    };
  },
  props: {
    cards: Array
  },
  methods: {
    addCard() {
      this.$router.push('/AddCard')
    },
    pushCard(card) {
      this.card = card
    }
  }
}
</script>

<style scoped>
  .add-new-card-btn {
    position: absolute;
    border: 2px solid #000000;
    border-radius: 5%;
    padding: 1%;
  text-align: center;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
    text-transform: uppercase;
    color: #000000;
    cursor: pointer;
    height: 80px;
width: 382px;
left: 450px;
top: 799px;
border-radius: 8px;

  }
</style>