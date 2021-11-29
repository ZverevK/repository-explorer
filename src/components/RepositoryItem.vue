<template>
  <div class="mt-2 p-2 border-2 border-green-400 rounded-md bg-gray-100">
    <div class="flex flex-row">
      <a class="font-bold p-2 bg-green-400 rounded-md hover:bg-green-500"
         :href="repository.html_url"
         target="_blank">
        {{ repository.name }}
      </a>
      <p class="p-2"> by </p>
      <a class="font-bold p-2 bg-green-400 rounded-md hover:bg-green-500"
         :href="repository.owner.html_url"
         target="_blank">
        {{ repository.owner.login }}
      </a>
    </div>
    <div>Lang: {{ repository.language }}</div>
    <div>Stars: {{ repository.stargazers_count }}</div>
    <div>{{ repository.description }}</div>

  </div>
</template>

<script>
export default {
  name: 'repository-item',
  props: {
    repository: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style scoped>

</style>
