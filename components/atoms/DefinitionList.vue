<template>
  <div>
    <dl>
      <dt>{{ dt }}</dt>
      <dd class="dd" v-html="dd"></dd>
    </dl>
  </div>
</template>

<script>
  export default {
    props: ['dt', 'dd']
  }
</script>

<style lang="scss" scoped>
  div {
    margin: 0 auto 40px;
    overflow: hidden;
    font-size: 1.2rem;
  }
  dl {
    display: flex;
  }
  dt {
    width: 35%;
    letter-spacing: .05em;
  }
  dd {
    width: 65%;
    color: #868686;
    line-height: 1.8;
    letter-spacing: .05em;
  }
  .dd {
    /deep/ .googlemap {
      color: #868686;
      letter-spacing: 1px;
      text-decoration: none;
    }
  }
</style>
