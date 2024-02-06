<script>
export default {
    name: "PokemonCard",
    props: {
        name: String,
        image: String,
        type1: String,
        type2: String,
        ability: String,
        life: Number,
        def: Number,
        atk: Number,
        serial: Number,
    }
}

</script>


<template>
    <div class="card">
        <h3>{{ name }}</h3>
        <span class="serial">{{ serial }}</span>
        <picture>
            <img :src="image" :alt="name">
        </picture>

        <div class="info">
            <span class="type">Tipo: {{ type1 }}</span>
            <span class="type">Abilità principale: {{ ability }}</span>
            <ul class="abilità d-flex">
                <li>Vita: {{ life }}</li>
                <li>Dif: {{ def }}</li>
                <li>Att: {{ atk }}</li>
            </ul>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.card {
    flex-basis: calc(100% / 3);
    flex-shrink: 0;
    flex-grow: 0;
    position: relative;

    background-color: goldenrod;

    height: 300px;

    .serial {
        position: absolute;
        right: 7px;
        top: 0;

        display: flex;
        align-items: center;
        justify-content: center;

        padding: 3px;

        width: 20px;
        height: 20px;
        font-weight: bold;
    }

    h3 {
        text-align: center;
        font-size: 1.2rem;
    }

    picture {
        width: auto;
        height: 150px;
        text-align: center;

        background-color: white;

        img {
            height: 100%;
            width: auto;
            max-width: 100%;
        }
    }

    .type {
        font-weight: 600;
        font-size: 0.8rem;
        padding: 3px 0;
        display: block;
    }

    .info {
        padding: 5px 0;

        ul {
            justify-content: center;
            padding-left: 0;
        }

        li {
            background-color: rgba(255, 0, 0, 0.24);

            text-align: center;
            font-weight: 700;
            color: white;

            border: 1px solid black;
            flex-basis: calc(100% / 3);
        }
    }

}
</style>