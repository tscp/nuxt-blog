<template>
  <div>
    <h2>{{ name }}</h2>
    <p>{{ sub }}</p>
  </div>
</template>

<script>
  export default {
    props: ['name', 'sub']
  }
</script>

<style lang="scss" scoped>
  div {
    margin: 0 auto;
  }
  h2 {
    letter-spacing: 0.1em;
    font-size: 5rem;
    font-weight: normal;
    font-family: "Ropa Sans", sans-serif;
    margin-bottom: 0.25em;
    position: relative;
    line-height: 1;
  }
  p {
    margin-bottom: 1.5rem;
    font-weight: bold;
    letter-spacing: .03em;
    font-size: 2rem;
  }
</style>
