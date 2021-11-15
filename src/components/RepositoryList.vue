<template>
  <h2 class="text-red-600" v-show="error">
    Произошла ошибка {{ errorMsg }}
  </h2>
  <div class="p-2" v-show="repositories.length">
    <h2 class="mt-2" v-show="repositories.length">
      Найдено репозиториев: {{ repositories.length }}
    </h2>
    <repository-item
      v-for="repository in repositories"
      :key="repository.id"
      :repository="repository"></repository-item>
  </div>
</template>

<script>
import RepositoryItem from './RepositoryItem.vue';

export default {
  props: {
    repositories: {
      type: Array,
      required: true,
    },
    error: {
      type: Boolean,
      required: true,
    },
    errorMsg: {
      type: String,
      required: true,
    },
  },
  name: 'repository-list',
  components: { RepositoryItem },
};
</script>

<style scoped>

</style>
