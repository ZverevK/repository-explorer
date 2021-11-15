<template>
  <form @submit.prevent class="flex flex-col
  xsm:flex-row">
    <my-input v-model="value" placeholder="Найти репозитории"/>
    <my-button @click="addValue">Поиск</my-button>
  </form>
</template>

<script>
export default {
  name: 'search-form',
  data() {
    return {
      value: '',
    };
  },
  methods: {
    addValue() {
      this.$emit('getValue', this.value);
      this.value = '';
    },
  },
};
</script>

<style scoped>

</style>
