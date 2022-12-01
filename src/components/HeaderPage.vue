<template>
  <header>
    <h1 class="title">
      BoolFlix
    </h1>
    <form @submit.prevent="$emit('queryChange', queryString)">
      <div class="search-bar">
        <label for="query">
          <input
            id="query"
            v-model="queryString"
            type="text"
            name="query"
            placeholder="Titolo"
          >
        </label>

        <button>Cerca</button>
      </div>
    </form>
  </header>
</template>

<script>
export default {
  name: 'HeaderPage',
  data() {
    return {
      queryString: '',
    };
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

button {
  background-color: red;
  padding: .3rem;
  margin-left: 1rem;
  color: white;
}

button:hover {
  cursor: pointer;
}
</style>
