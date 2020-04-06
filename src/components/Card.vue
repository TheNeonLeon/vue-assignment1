<template>
<article v-bind:class="['card', vendor]" @click="clickCard()">
 <div class="wrapper">
 <div class="bitcoin" ref="bitcoin" v-bind="changeCard">
    <img class="chip" src="@/assets/chip-dark.svg">
    <img class="bitcoin-logo" src="@/assets/vendor-bitcoin.svg">
    <p class="card-number">{{number}}</p>
    <p class="cardholder">{{name}}</p>
    <p class="cardholder">{{expiration}}</p>
  </div>
 </div>
</article>
</template>

<script>
export default {
  name: 'Card',
  data: () => {
    /* default inputs for card */
    return {
      defaultNumber: 'xxxx xxxx xxxx xxxx',
      defaultName: 'Firstname Lastname',
      defaultExpiration: 'MM/YY',
      defaultVendor: '',
      ccv: ''
    }
  },
  props: {
    card: Object
  },
  methods: {
    clickCard () {
      this.$emit('clickCard', this.card)
    }
  },
  computed: {
    number () {
      if (!this.card.number) {
        return this.defaultNumber
      } else {
        let cardNumber = this.card.number
        cardNumber = cardNumber.match(/.{1,4}/g)
        return cardNumber.join(' ')
      }
    },
    name () {
      if (!this.card.name) {
        return this.defaultName
      } else {
        return this.card.name
      }
    }
  }
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
</style>
