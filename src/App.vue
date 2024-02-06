<script>
import AppNavigation from './components/AppNavigation.vue'
import PokemonList from './components/PokemonList.vue'


export default {
  name: "Yu-Gi-Oh",
  data: () => ({
  }),
  components: {
    AppNavigation, PokemonList
  }
}

</script>

<template>
  <div class="container-fluid">

    <header>
      <h1 class="text-center">Pokévuex</h1>
      <h5 class="text-center">Scegli un tipo di Pokemon:</h5>
    </header>

    <AppNavigation />
    <PokemonList />

  </div>
</template>

<style lang="scss">
@use './assets/scss/style.scss';

h1 {
  font-weight: 700;
  font-size: 3rem;
  margin: 50px 0;
  color: rgb(235, 10, 10);
}
</style>
