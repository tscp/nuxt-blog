<template>
  <label>
    <span v-if="$slots.label"><slot name="label"></slot></span>
    <span v-else-if="label">{{ label }}</span>
    <input :type="type"
           :name="name"
           :value="value"
           @input="updateValue"
           @focus="$emit('focus', $event)"
           @blur="$emit('blur', $event)"
     />
  </label>
</template>

<script>
  export default {
    props: {
      value: {},
      label: { type: String },
      name: { type: String, require: true },
      type: { type: String, default: 'text' },
      placeholder: { type: String }
    },
    methods: {
      updateValue (e) {
        this.$emit('input', e.target.value);
        this.$emit('change', e.target.value);
      }
    }
  }
</script>

<style lang="scss" scoped>
  label {
    display: flex;
    align-items: center;
  }
  span {
    padding-right: 10px;
  }
  input {
    border-radius: 4px;
    border: 1px solid #cecece;
    margin-right: 20px;
    padding: 5px;
  }
</style>
