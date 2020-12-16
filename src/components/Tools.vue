<template>
    <nav>
        <input type="text" placeholder="Search..." v-model="search" v-on:input="filterItems">
        Sort by
        <button v-on:click="sortAlphabetical">Name</button>
        <button v-on:click="sortOldest">Oldest first</button>
        <button v-on:click="sortNewest">Newest first</button>
    </nav>
</template>

<script>
export default {
    name: 'Tools',
    data() {
        return {
            search: '',
        }
    },
    methods: {
        filterItems() {
            this.$emit('filter-items', this.search)
        },
        sortAlphabetical() {
            this.$emit('sort-alpha', 'ALPHA')
        },
        sortNewest() {
            this.$emit('sort-new', 'NEW')
        },
        sortOldest() {
            this.$emit('sort-old', 'OLD')
        },
    }
}
</script>

<style scoped>

</style>