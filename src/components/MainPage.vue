<template>
  <main>
    <ul
      v-for="element in arrayMovies"
      :key="element.id"
    >
      <li>{{ element.title }}</li>
      <!-- <li>{{ element.original_title }}</li> -->
      <li>{{ element.original_language }}</li>
      <li>{{ element.vote_average }}</li>
    </ul>
  </main>
</template>

<script>

export default {
  name: 'MainPage',
  props: {
    arrayMovies: Array,
  },
};
</script>

<style lang="scss" scoped>

main {
  height: calc(100vh - 70px);
  overflow-y: auto;
}
</style>
