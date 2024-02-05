<script>
import AppHeader from './components/AppHeader.vue'
import PokemonList from './components/PokemonList.vue'


export default {
  name: "Yu-Gi-Oh",
  data: () => ({
  }),
  components: {
    AppHeader, PokemonList
  }
}

</script>

<template>
  <div class="container-fluid">
    <AppHeader />
    <PokemonList />
  </div>
</template>

<style lang="scss">
@use './assets/scss/style.scss';
</style>
