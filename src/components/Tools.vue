<template>
    <nav>
        <input type="text" placeholder="Search..." v-model="search" v-on:input="filterItems">
        Sort by
        <button>Highest rated</button>
        <button>Title</button>
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
        }
    }
}
</script>

<style scoped>

</style>