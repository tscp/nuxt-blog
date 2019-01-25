<template>
  <div>
    <dl class="cls">
      <dt>{{ label }}</dt>
      <dd><slot></slot></dd>
    </dl>
  </div>
</template>

<script>
  export default {
    value: {},
    props: ['label', 'cls']
  }
</script>

<style lang="scss" scoped>
  dl {
    align-items: center;
    font-size: 1.2rem;
    display: flex;
    padding: 0 0 20px;
    margin: 0 0 20px;
    border-bottom: 1px solid #a0a0a0;
  }
  dt {
    font-weight: bold;
    padding-right: 40px;
    width: 25%;
  }
  dd {
    width: 75%;
    display: flex;
  }
  .address {
    > dl {
      align-items: start;
      > dt {
        padding-top: 5px;
      }
      > dd {
        display: block;
      }
    }
  }
</style>
