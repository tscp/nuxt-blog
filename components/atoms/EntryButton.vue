<template>
  <div>
    <a href="url">
      <p class="en-title">ENTRY HERE</p>
      <p class="jp-title">応募はこちらから</p>
    </a>
  </div>
</template>

<script>
  export default {
    props: ['url']
  }
</script>

<style lang="scss" scoped>
  div {
    margin: 58px auto 0;
    a {
      background-color: #e5e5e5;
      display: block;
      padding: 40px 0 33px;
      text-align: center;
      text-decoration: none;
      width: 100%;
      transition: all .4s;
      &:hover {
        opacity: .5;
      }
    }
    p {
      letter-spacing: .05em;
    }
    .en-title {
      color: #000;
      font-family: "Ropa Sans", sans-serif;
      font-weight: normal;
      font-size: 3rem;
      margin-bottom: 3px;
    }
    .jp-title {
      color: #000;
      font-size: 1.2rem;
    }
  }
</style>
