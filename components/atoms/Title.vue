<template>
  <div>
    <h1>{{ name }}</h1>
  </div>
</template>

<script>
  export default {
    props: ['name']
  }
</script>

<style lang="scss" scoped>
  h1 {
    width: 100%;
    height: auto;
    padding: 80px 0;
    text-align: center;
    font-family: "Ropa Sans", sans-serif;
    letter-spacing: 0.2em;
    line-height: 1;
    font-size: 3rem;
    margin-top: 90px;
  }
</style>
