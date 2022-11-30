<template>
  <div class="container">
    <header>
      <h1 class="title">
        BoolFlix
      </h1>
      <div class="search-bar">
        <label for="s">
          <input
            id="s"
            type="search"
            name="s"
            placeholder="Titolo"
          >
        </label>

        <button>Cerca</button>
      </div>
    </header>

    <main>
      ciao
    </main>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'MainPage',
  data() {
    return {
      arrMovies: null,
      urlApi: 'https://api.themoviedb.org/3/movie/550?api_key=57cd305b946d02e5d2beaa28935d945e',
    };
  },
  created() {
    axios.get(this.urlApi)
      .then((axiosResponse) => {
        console.log(axiosResponse);
        this.arrMovies = axiosResponse.data.response;
      });
  },
};
</script>

<style lang="scss" scoped>
header {
  background-color: black;
  color: red;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem 2rem;
}

main {
  height: calc(100vh - 70px);
  overflow-y: auto;
}
</style>
