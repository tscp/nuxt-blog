<template>
  <div class="group">
    <label v-if="$slots.label"><slot name="label"></slot></label>
    <label v-else-if="label">{{ label }}</label>
    <slot></slot>
  </div>
</template>

<script>
  export default {
    props: {
      value: {},
      label: { type: String }
    }
  }
</script>

<style lang="scss" scoped>

</style>
