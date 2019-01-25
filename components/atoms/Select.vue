<template>
  <label>
    <span v-if="cls !== 'date'">
      <span v-if="$slots.label"><slot name="label"></slot></span>
      <span v-else-if="label">{{ label }}</span>
    </span>
    <select :name="name"
            :value="value"
            @input="updateValue"
            @focus="$emit('focus', $event)"
            @blur="$emit('blur', $event)"
     >
      <slot :options="options"></slot>
    </select>
    <span v-if="cls === 'date'">
      <span v-if="$slots.label"><slot name="label"></slot></span>
      <span v-else-if="label">{{ label }}</span>
    </span>
  </label>
</template>

<script>
  export default {
    props: {
      value: {},
      label: { type: String },
      name: { type: String, require: true },
      options: { type: Array, require: true },
      cls: { type: String }
    },
    methods: {
      updateValue (e) {
        let value = e.target.selectedOptions.length ? e.target.selectedOptions[0]._value : null;
        this.$emit('input', value);
        this.$emit('selected', value);
      }
    }
  }
</script>

<style lang="scss" scoped>
  label {
    margin-right: 20px;
  }
  select {
    margin-right: 10px;
  }
</style>
