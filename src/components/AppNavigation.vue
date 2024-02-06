<script>

import SearchForm from '../components/SearchForm.vue'


export default {
    name: "AppNavigation",
    data: () => ({
        imageTypes: [
            {
                type: "Grass",
                img: "/bulbasaur.jpg"
            },
            {
                type: "Fire",
                img: "/charmender.jpg"
            },
            {
                type: "Electric",
                img: "/pikachu.jpg"
            },
            {
                type: "Water",
                img: "/squirtle.jpg"
            },
            {
                type: "Bug",
                img: "/caterpie.jpg"
            },
            {
                type: "Dark",
                img: "/rattata.jpg"
            },
            {
                type: "Dragon",
                img: "/dragonite.jpg"
            },
            {
                type: "Fairy",
                img: "/clefairy.jpg"
            },
            {
                type: "Fighting",
                img: "/machop.jpg"
            },
            {
                type: "Flying",
                img: "/corvisquire.jpg"
            },
            {
                type: "Ghost",
                img: "/gengar.jpg"
            },
            {
                type: "Ground",
                img: "/dugtrio.jpg"
            },
            {
                type: "Ice",
                img: "/articuno.jpg"
            },
            {
                type: "Normal",
                img: "/pidgey.jpg"
            },
            {
                type: "Poison",
                img: "/nidoran-m.jpg"
            },
            {
                type: "Psychic",
                img: "/hypno.jpg"
            },
            {
                type: "Rock",
                img: "/onix.jpg"
            },
            {
                type: "Steel",
                img: "/aron.jpg"
            },
        ]
    }),
    components: {
        SearchForm
    },
    emits: ['pokemon-type-click', 'submit-search-text']
};
</script>

<template>
    <nav class="d-flex flex-wrap mb-3">
        <ul class="d-flex pb-4">
            <li role="button" v-for="image in imageTypes" @click="$emit('pokemon-type-click', image.type)">
                <img :src="image.img" :alt="image.type">
                <span class="text-center">{{ image.type }}</span>
            </li>
        </ul>

        <SearchForm placeholder="Cerca un pokemon..." @submit-search-text="$emit('submit-search-text', lowercasedText)" />

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