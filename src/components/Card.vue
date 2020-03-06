<template>
 <div>
  <div class="bitcoin" v-bind="changeCard">
    <img class="chip" src="@/assets/chip-dark.svg">
    <img class="bitcoin-logo" src="@/assets/vendor-bitcoin.svg">
    <p class="card-number">1234 5435 4666 0931</p>
    <p></p>
  </div>
 </div>   
</template>

<script>
export default {
    
}
</script>

<style scoped>
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
</style>