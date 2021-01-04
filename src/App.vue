<template>
  <div>
    <router-view class="wallet" @card="addCards" :cards="cards"/>
  </div>
</template>

<script>
export default {
  data() {
    return {
      cards: []
    }
  },
  methods: {
    addCards(card) {
      this.cards.push(card);
    }
  }
}
</script>

<style>
  .wallet {
    background: #FFFFFF;
  }
</style>