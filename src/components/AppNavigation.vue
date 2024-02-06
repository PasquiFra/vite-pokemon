<script>
import { store } from '../data/store';

import axios from "axios";

export default {
    name: "AppHeader",
    data: () => ({
        imageTypes: [
            {
                type: "Grass",
                img: "public/bulbasaur.jpg"
            },
            {
                type: "Fire",
                img: "public/charmender.jpg"
            },
            {
                type: "Electric",
                img: "public/pikachu.jpg"
            },
            {
                type: "Water",
                img: "public/squirtle.jpg"
            },
            {
                type: "Bug",
                img: "public/caterpie.jpg"
            },
            {
                type: "Dark",
                img: "public/rattata.jpg"
            },
            {
                type: "Dragon",
                img: "public/dragonite.jpg"
            },
            {
                type: "Fairy",
                img: "public/clefairy.jpg"
            },
            {
                type: "Fighting",
                img: "public/machop.jpg"
            },
            {
                type: "Flying",
                img: "public/corvisquire.jpg"
            },
            {
                type: "Ghost",
                img: "public/gengar.jpg"
            },
            {
                type: "Ground",
                img: "public/dugtrio.jpg"
            },
            {
                type: "Ice",
                img: "public/articuno.jpg"
            },
            {
                type: "Normal",
                img: "public/pidgey.jpg"
            },
            {
                type: "Poison",
                img: "public/nidoran-m.jpg"
            },
            {
                type: "Psychic",
                img: "public/hypno.jpg"
            },
            {
                type: "Rock",
                img: "public/onix.jpg"
            },
            {
                type: "Steel",
                img: "public/aron.jpg"
            },
        ],
        searchText: "",
    }),


    methods: {
        fetchPokemons(type) {
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
    <nav class="d-flex flex-wrap mb-3">
        <ul class="d-flex pb-4">
            <li role="button" v-for="image in imageTypes" @click="fetchPokemons(image.type)">
                <img :src="image.img" :alt="image.type">
                <span class="text-center">{{ image.type }}</span>
            </li>
        </ul>
        <input class="form-control w-50 my-2" type="text" placeholder="Cerca un pokemon" v-model="searchText">
    </nav>
</template>

<style lang="scss" scoped>
nav {
    height: 35vh;
    justify-content: center;

    ul {
        overflow-x: auto;
        width: 100%;
        max-width: 100%;
        background-color: #FFE9B8;
    }

    li {
        margin: 0 5px;
        border: 1px solid goldenrod;

        box-shadow: 2px 2px goldenrod;
        width: 200px;
        height: 220px;

        flex-shrink: 0;
    }

    img {
        text-align: center;
        height: 90%;
        width: 100%;

        background-color: #FFE9B8;
    }
}
</style>