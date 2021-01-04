<template>
    <header>
        <h1 class="heading"> {{ h1 }} </h1>
        <h5 class="new-card-heading"> {{ h5 }} </h5>
    </header>
</template>

<script>
export default {
    name: "Top",
    props: {
        h1: String,
        h5: String
    }
}
</script>

<style scoped>
  .heading {
    color: #222222;
    font-weight: bold;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    text-transform: uppercase;
  }
  
  .new-card-heading {
    color: rgba(131, 131, 131, 0.6);
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
  }
</style>