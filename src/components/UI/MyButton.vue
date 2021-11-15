<template>
  <button class="w-full p-2 mt-2 bg-green-500 rounded-md
  xsm:mt-0 xsm:rounded-l-none xsm:w-1/3
  hover:bg-green-600">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: 'my-button',
};
</script>

<style scoped>

</style>
