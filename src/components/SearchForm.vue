<script>
export default {
    name: "AppNavigation",
    data: () => ({
        text: "",
    }),
    computed: {
        lowercasedText() {

            return this.text.toLowerCase()
        }
    },
    props: {
        placeholder: String,
    },
    emits: ['submit-search-text']


}
</script>

<template>
    <form class="w-50" action="" @submit.prevent="$emit('submit-search-text', lowercasedText)">
        <input class="form-control" type="text" :placeholder="placeholder" v-model.trim="text">
    </form>
</template>


<style lang="scss" scoped></style> 