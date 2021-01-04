<template>
  <div v-on:input="changeCard">

<form>
    <label class="cardnumber" for="cardnumber">Card Number</label>
    <input class="cardnumber-input-field" v-model="cardnumber" type="text" name="cardnumber" placeholder="XXXX XXXX XXXX XXXX" maxlength="16"/>

    <label class="cardholder" for="cardholder">Cardholder Name</label>
    <input class="cardholder-input-field" v-model="cardholder" type="text" name="cardholder" placeholder="FIRSTNAME LASTNAME" maxlength="30"/>

    <label class="validity" for="validity">Valid Thru</label>
    <input class="validity-input-field" v-model="validity" type="text" name="validity" placeholder="MM/YY" maxlength="5"/>
    
    <label class="ccv" for="ccv">CCV</label>
    <input class="ccv-input-field" v-model="ccv" type="text" name="ccv" placeholder="xxx" maxlength="3"/>

        <label class="vendor" for="vendor"> Vendor</label>
    <select class="vendor-input-field" v-model="vendor" name="vendor">
      <option value="bitcoin">Bitcoin</option>
      <option value="ninja">Ninja</option>
      <option value="blockchain">Block Chain</option>
      <option value="evil">Evil Corp</option>
    </select>
</form>
  </div>
</template>

<script>
export default {
  data: () => {
    return {
      vendor: '',
      cardnumber: '',
      cardholder: '',
      validity: '',
      ccv: ''
    }
  },
  methods: {
    changeCard() {
      const input = {
        vendor: this.vendor,
        cardnumber: this.cardnumber,
        cardholder: this.cardholder,
        validity: this.validity,
        ccv: this.ccv
      }
      this.$emit("changeCard", input);
    }
  }
};
</script>

<style scoped>
  .cardnumber {
    position: absolute;
    width: 251px;
    height: 22px;
    left: 400px;
    top: 507px;
    text-transform: uppercase;
    color:black;
  }
  .cardnumber-input-field {
    position: absolute;
    width: 382px;
    height: 56px;
    left: 400px;
    top: 528px;
    border: 1px solid black;
    box-sizing: border-box;
    border-radius: 3px;
  }
  .cardholder {
    position: absolute;
    width: 251px;
    height: 22px;
    left: 400px;
    top: 594px;
    display: flex;
    align-items: center;
    text-transform: uppercase;
    color:black;
  }
  .cardholder-input-field {
    position: absolute;
    width: 382px;
    height: 56px;
    left: 400px;
    top: 615px;
    border: 1px solid black;
    box-sizing: border-box;
    border-radius: 3px;
  }
  .validity {
    position: absolute;
    width: 175px;
    height: 22px;
    left: 400px;
    top: 683px;
    line-height: 13px;
    display: flex;
    align-items: center;
    text-transform: uppercase;
    color: black;
  }
  .validity-input-field {
    position: absolute;
    width: 175px;
    height: 56px;
    left: 400px;
    top: 704px;
    border: 1px solid black;
    box-sizing: border-box;
    border-radius: 3px;
  }
  .ccv {
    position: absolute;
    width: 175px;
    height: 22px;
    left: 700px;
    top: 683px;
    line-height: 13px;
    display: flex;
    align-items: center;
    text-transform: uppercase;
    color:black;
  }
  .ccv-input-field {
    position: absolute;
    width: 175px;
    height: 56px;
    left: 700px;
    top: 704px;
    border: 1px solid black;
    box-sizing: border-box;
    border-radius: 3px;
  }
  .vendor {
    position: absolute;
    width: 382px;
    height: 22px;
    left: 400px;
    top: 780px;
    line-height: 13px;
    text-transform: uppercase;
    color: black;
  }
  .vendor-input-field {
    position: absolute;
    width: 382px;
    height: 56px;
    left: 400px;
    top: 800px;
    border: 1px solid black;
    border-radius: 3px;
  }
</style>