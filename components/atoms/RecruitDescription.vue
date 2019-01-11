<template>
  <div>
    <dl v-for="(value, key) in description">
      <dt>{{ key }}</dt>
      <dd v-html="value"></dd>
    </dl>
  </div>
</template>

<script>
  export default {
    props: ['description']
  }
</script>

<style lang="scss" scoped>
  div {
    margin: 0 auto;
    padding-top: 20px;
  }
  dl {
    border-bottom: solid 1px #e5e5e5;
    font-size: 1.2rem;
    display: flex;
    letter-spacing: .05em;
    line-height: 1.6;
    margin-top: 20px;
    padding-bottom: 20px;
  }
  dt {
    width: 20%;
  }
  dd {
    width: 80%;
    /deep/ strong {
      font-weight: normal;
    }
  }
</style>
