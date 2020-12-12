<template>
    <header>
        <h1 class="title"> {{ h1 }} </h1>
        <h5 class="new-card-title"> {{ h5 }} </h5>
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
  .title {
    color: #222222;
    font-weight: bold;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    text-transform: uppercase;
  }
  
  .new-card-title {
    color: rgba(131, 131, 131, 0.6);
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
  }
</style>