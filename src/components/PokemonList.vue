<script>
import { store } from '../data/store';
import PokemonCard from "./PokemonCard.vue";


export default {
    name: "PokemonList",
    data: () => ({
        pokemons: store.pokemons
    }),
    components: {
        PokemonCard
    }

}

</script>

<template>
    <section>
        <ul class="row row-cols-md-5 g-3">
            <li class="col" v-for="pokemon in pokemons" :key="pokemon.id">
                <PokemonCard :name="pokemon.name" :image="pokemon.imageUrl" :type1="pokemon.type1" :type2="pokemon.type2"
                    :ability="pokemon.ability1" :life="pokemon.hp" :atk="pokemon.atk" :def="pokemon.def"
                    :serial="pokemon.serial" />
            </li>
        </ul>
    </section>
</template>

<style lang="scss" scoped>
.row {
    justify-content: center;
}

section {
    border-top: 1px solid black;
    padding: 20px;
}
</style>