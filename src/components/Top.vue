<template>
<header class="home-header">
    <h1>{{h1}}</h1>
    <p>{{paragraph}}</p>
</header>
</template>
<script>
export default {
  name: 'Top',
  props: {
    h1: String,
    paragraph: String
  }
}
</script>

<style scoped>

</style>
