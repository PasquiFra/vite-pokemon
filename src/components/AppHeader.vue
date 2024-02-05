<script>
import { store } from '../data/store';

import axios from "axios";

export default {
    name: "AppHeader",
    methods: {
        fetchPokemons(type) {
            const endpoint = `https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons?eq[type1]=${type}`;
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
    <header>
        <h1 class="text-center">Pokévuex</h1>
        <h5 class="text-center">Scegli un tipo di Pokemon:</h5>
        <div id="jumbotron" class="d-flex">
            <ul class="d-flex">
                <li role="button" @click="fetchPokemons('Grass')">
                    <img src="../../bulbasaur.jpg" alt="bulbasaur">
                </li>
                <li role="button" @click="fetchPokemons('Fire')">
                    <img src="../../charmender.jpg" alt="charmender">
                </li>
                <li role="button" @click="fetchPokemons('Water')">
                    <img src="../../squirtle.jpg" alt="squirtler">
                </li>
                <li role="button" @click="fetchPokemons('Electric')">
                    <img src="../../pikachu.jpg" alt="pikachu">
                </li>
            </ul>
        </div>
    </header>
</template>

<style lang="scss" scoped>
h1 {
    font-weight: 700;
    font-size: 3rem;
    margin: 50px 0;
    color: rgb(235, 10, 10);
}

#jumbotron {
    height: 25vh;
    justify-content: center;

    li {
        margin: 0 5px;
        border: 1px solid goldenrod;

        box-shadow: 2px 2px goldenrod;
        width: 200px;
        height: 200px;
    }

    img {
        text-align: center;
        height: 100%;
        width: 100%;
    }
}
</style>