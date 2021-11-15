<template>
  <div class="p-2 lg:w-2/3 lg:mx-auto">
    <search-form @getValue="getRepositories"></search-form>
    <repository-list :repositories="repositories"
                     :error="error"
                     :errorMsg="errorMsg"></repository-list>
  </div>
</template>

<script>
import axios from 'axios';
import SearchForm from './components/SearchForm.vue';
import RepositoryList from './components/RepositoryList.vue';

export default {
  name: 'App',
  data() {
    return {
      repositories: [],
      error: false,
      errorMsg: '',
    };
  },
  components: { RepositoryList, SearchForm },
  methods: {
    async getRepositories(value) {
      try {
        const response = await axios.get(`https://api.github.com/search/repositories?q=${value}`);
        this.repositories = response.data.items;
      } catch (e) {
        this.error = true;
        this.errorMsg = e.message;
      }
    },
  },
};
</script>

<style>
</style>
