<script>
export default {
    name: "AppHeader",
    methods: {

    }
}
</script>

<template>
    <header>
        <h1 class="text-center">Pokévuex</h1>
        <h5 class="text-center">Scegli un tipo di Pokemon:</h5>
        <div id="jumbotron" class="d-flex">
            <ul class="d-flex">
                <li role="button" @click="fetchPokemons('grass')">
                    <img src="../../public/bulbasaur.jpg" alt="bulbasaur">
                </li>
                <li role="button" @click="fetchPokemons('fire')">
                    <img src="../../public/charmender.jpg" alt="charmender">
                </li>
                <li role="button" @click="fetchPokemons('water')">
                    <img src="../../public/squirtle.jpg" alt="squirtler">
                </li>
                <li role="button" @click="fetchPokemons('electricity')">
                    <img src="../../public/pikachu.jpg" alt="pikachu">
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

    ul {
        list-style-type: none;
    }

    li {
        border: 1px dotted goldenrod;
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