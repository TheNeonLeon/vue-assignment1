<template>
  <article class="card" v-on:click="pushCard()" v-bind:class="['card', vendor, chip]">
    <div>
      <img class="chip-pic" v-bind:src="require(`../assets/chip-${chip}.svg`)">
      <img class="vendor-pic" v-bind:src="require(`../assets/vendor-${vendor}.svg`)">
    </div>

    <div>
      <p class="cardnumber"> {{ cardnumber }} </p>
    </div>

    <div>
      <p class="cardholder-text">Cardholder Name</p>
      <p class="cardholder"> {{ cardholder }} </p>
    </div>

    <div>
      <p class="validity-text">Valid thru</p>
      <p class="validity"> {{ validity }} </p>
    </div>
  </article>
</template>

<script>
export default {
  name: "Card",
  props: {
    card: Object
  },
  data: () => {
    return {
      defaultVendor: "",
      defaultNumber: "xxxx xxxx xxxx xxxx",
      defaultHolder: "Firstname/Lastname",
      defaultValidity: "MM/YY"
    };
  },
  computed: {
    cardnumber() {
      if (!this.card.cardnumber) {
        return this.defaultNumber;
      } else {
        let number = this.card.cardnumber
        number = number.match(/.{1,4}/g)   
        return number.join(' ');
      }
    },
    cardholder() {
      if (!this.card.cardholder) {
        return this.defaultHolder;
      } else {
        return this.card.cardholder;
      }
    },
    validity() {
      if (!this.card.validity) {
        return this.defaultValidity;
      } else {
        return this.card.validity;
      }
    },
    vendor() {
      if (!this.card.vendor) {
        return this.defaultVendor;
      } else {
        return this.card.vendor;
      }
    },
    chip() {
      let chip = "dark";
      if (!this.card.vendor) {
        return chip;
      } else if (this.card.vendor === "bitcoin") {
        return chip;
      } else {
        chip = "light";
        return chip;
      }
    }
  },
  methods: {
    pushCard() {
      this.$emit("pushCard", this.card)
    }
  }
}
</script>

<style scoped>
  .card {
    position: absolute;
    width: 382px;
    height: 241px;
    left: 400px;
    top: 150px;
    display: flex;
    flex-wrap: wrap;
  justify-content: center;
  }
  
  .chip-pic {
    position: absolute;
    width: 70px;
    height: 60px;
    left: 20px;
    top: 20px;
  }
  .vendor-pic  {
    position: absolute;
    left: 80%;
    right: 10%;
    top: 14%;
  }
  .bitcoin {
    background: linear-gradient(rgba(255, 255, 255, 0.15), rgba(255, 255, 255, 0)), #FFAE34;
    border-radius: 8px;
    color: #000000;
  }
  .ninja {
    background: linear-gradient( rgba(255, 255, 255, 0.15), rgba(255, 255, 255, 0)), #222222;
    border-radius: 8px;
    color: #FFFFFF;
  }
  .blockchain {
    background: linear-gradient( rgba(0, 0, 0, 0.15), rgba(0, 0, 0, 0) 100%), #8B58F9;
    border-radius: 8px;
    color: #000000;
  }
  .evil {
    background: linear-gradient( rgba(0, 0, 0, 0.16), rgba(0, 0, 0, 0) 100%), #F33355;
    border-radius: 2px;
    color: #FFFFFF;
  }
  .dark {
    color: #222222;;
    text-shadow: -0.5px 0.5px 0px #3a3a3a;
  }
  .light {
    color: #FFFFFF;
    text-shadow: 0.5px 0.5px 0px #868686, -0.5px -0.5px 0px #868686;
  }
  .cardnumber {
    position: absolute;
    width: 350px;
    height: 42px;
    left: 55px;
    top: 80px;
    font-size: 29px;
    line-height: 32px;
    letter-spacing: 0.03em;
  }
  .cardholder-text {
    position: absolute;
    width: 251px;
    height: 16px;
    left: 32px;
    top: 155px;
    font-size: 15px;
    line-height: 13px;
    display: flex;
    align-items: center;
    text-transform: uppercase;
    color: rgba(128, 128, 128, 0.8);

  }
  .cardholder {
    position: absolute;
    width: 251px;
    height: 32px;
    left: 32px;
    top: 170px;
    font-size: 15px;
    line-height: 20px;
    display: flex;
    align-items: center;
    text-transform: uppercase;
  }
  .validity-text {
    position: absolute;
    width: 89px;
    height: 16px;
    left: 260px;
    top: 155px;
    font-size: 15px;
    line-height: 13px;
    display: flex;
    align-items: center;
    text-align: right;
    text-transform: uppercase;
    color: rgba(128, 128, 128, 0.8);
    
  }
  .validity {
    position: absolute;
    font-family: 'PT Mono';
    font-style: normal;
    font-size: 18px;
    line-height: 20px;
    display: flex;
    align-items: center;
    text-align: right;
    text-transform: uppercase;
    height: 32px;
    width: 89px;
    left: 290px;
    top: 180px;

  }
</style>