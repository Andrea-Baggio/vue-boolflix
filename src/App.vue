<template>
  <div class="body">
    <HeaderPageVue @queryChange="search" />
    <MainPageVue :array-movies="arrMovies" />
  </div>
</template>

<script>
import axios from 'axios';
import MainPageVue from './components/MainPage.vue';
import HeaderPageVue from './components/HeaderPage.vue';

export default {
  name: 'App',
  components: {
    MainPageVue,
    HeaderPageVue,
  },
  data() {
    return {
      baseApiUrl: 'https://api.themoviedb.org/3',
      apiKey: '57cd305b946d02e5d2beaa28935d945e',
      languageResults: 'it-IT',
      arrMovies: [],
    };
  },
  methods: {
    search(queryString) {
      axios.get(`${this.baseApiUrl}/search/movie`, {
        params: {
          api_key: this.apiKey,
          query: queryString,
          language: this.languageResults,
        },
      })
        .then((axiosResponse) => {
          this.arrMovies = axiosResponse.data.results;
          console.log(this.arrMovies);
        });
    },
  },
};
</script>
<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Lato:wght@100;300;400;700;900&display=swap');
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.body {
  background-color: gray;
  color: white;
  font-family: 'Lato', sans-serif;
}

</style>
