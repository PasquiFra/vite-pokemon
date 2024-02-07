<script>

export default {
    name: "SelectList",
    data: () => ({
        selectedOption: ""
    }),
    props: {
        defaultLabel: String,
        defaultvalue: String,
        options: Array
    },
    emits: ['option-change']
};

</script>


<template>
    <select class="my-1" v-model="selectedOption" @change="$emit('option-change', selectedOption)">
        <option :value="defaultvalue || ''">{{ defaultLabel || '---' }}</option>
        <option v-for="(option, i) in options" :key="i" :value="option.type">
            {{ option.type }}
        </option>
    </select>
</template>

<style lang="scss" scoped></style>