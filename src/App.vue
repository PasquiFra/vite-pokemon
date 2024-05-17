<script>
import AppNavigation from './components/AppNavigation.vue';
import PokemonList from './components/PokemonList.vue';
import { store } from './data/store';
import axios from "axios";

export default {
  name: "Pokemons",
  data: () => ({
    store
  }),
  components: {
    AppNavigation, PokemonList
  },
  methods: {
    callAxios(endpoint) {
      axios.get(endpoint).then(res => {
        store.pokemons = res.data.docs;
      })
    },
    FetchPokemons(type) {
      const endpoint = `https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons?eq[type1]=${type}&per=40`;

      this.callAxios(endpoint)
    },
    searchFilter(text) {

      const endpoint = `https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons?q[name]=${text}&per=20`;

      this.callAxios(endpoint)
    }

  }
}

</script>

<template>
  <div class="container-fluid">

    <header>
      <h1 class="text-center">Pokévuex</h1>
      <h5 class="text-center">Scegli un tipo di Pokemon:</h5>
    </header>

    <AppNavigation @option-change="FetchPokemons" @submit-search-text="searchFilter($event)" />

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
