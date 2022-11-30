<template>
  <div class="body">
    <MainPageVue />
  </div>
</template>

<script>
import MainPageVue from './components/MainPage.vue';

export default {
  name: 'App',
  components: {
    MainPageVue,
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
