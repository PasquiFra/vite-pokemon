<script>
import AppNavigation from './components/AppNavigation.vue';
import PokemonList from './components/PokemonList.vue';
import { store } from './data/store';
import axios from "axios";

export default {
  name: "Yu-Gi-Oh",
  data: () => ({
    store
  }),
  components: {
    AppNavigation, PokemonList
  },
  methods: {
    FetchPokemons(type) {
      console.log("chiamo...")

      const endpoint = `https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons?eq[type1]=${type}&per=40`;

      console.log(endpoint)

      axios.get(endpoint).then(res => {
        store.pokemons = res.data.docs;
        console.log(store)
      })
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

    <AppNavigation @pokemon-type-click="FetchPokemons" />

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
