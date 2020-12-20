<template>
    <section class="stack">
        <div class="cards" v-for="(card, index) in allCards" v-bind:key="index">
            <card 
              class="card" 
              v-bind:card="card"
              @pushCard="pushCard"
            />
        </div>
    </section>
</template>

<script>
import card from "../components/Card";
export default {
  name: "CardStack",
  components: {
    card
  },
  props: {
    allCards: Array
  },
  methods: {
    pushCard(card) {
      this.$emit('pushCard', card)
    }
  }  
}
</script>

<style scoped>
  .stack {
    position: absolute;
    left: 5px;
    top: 300px;
  }
  .cards {
    height: 4rem;
    overflow: visible;
    position: relative;
       
  }
  .cards:hover{
    z-index:10;
     transition:all 0.5s ease-in-out;
    -webkit-transition:all 0.2s ease-in-out;

  }
  .card {
    cursor: pointer;
  }
</style>