<template>
  <div class="tab-visual">
    <h3>{{ h3 }}</h3>
    <p>{{ p }}</p>
  </div>
</template>

<script>
  export default {
    props : ['h3', 'p']
  }
</script>

<style lang="scss" scoped>
  div {
    background-color: #000;
  }
  h3 {
    font-size: 3rem;
    margin-bottom: 6px;
    line-height: 1.5;
  }
  p {
    font-size: 1.2rem;
    line-height: 1.9;
    margin-bottom: 36px;
    width: 50%;
    white-space: pre-wrap;
    word-wrap: break-word;
  }
</style>
