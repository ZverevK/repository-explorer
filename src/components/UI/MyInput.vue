<template>
  <input class="w-full p-2 border-2 border-green-400 rounded-md
  xsm:rounded-r-none"
         :value="modelValue"
         @input="updateInput"
         type="text" />
</template>

<script>
export default {
  name: 'my-input',
  props: {
    modelValue: [String, Number],
  },
  methods: {
    updateInput(event) {
      this.$emit('update:modelValue', event.target.value);
    },
  },
};
</script>

<style scoped>

</style>
