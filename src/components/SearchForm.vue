<script>
export default {
    name: "AppNavigation",
    data: () => ({
        searchText: "",

    })

}
</script>

<template>
    <form action="">
        <input class="form-control w-50 my-2" type="text" placeholder="Cerca un pokemon" v-model="searchText">
    </form>
</template>


<style lang="scss" scoped></style> 