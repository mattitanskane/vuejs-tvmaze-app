<template>
    <nav>
        <input type="text" placeholder="Search episodes..." v-model="search" v-on:input="filterItems">
        <div>
            <p>Sort by</p>
            <button v-on:click="sortAlphabetical" class="btn btn-sort">Name</button>
            <button v-on:click="sortOldest" class="btn btn-sort">Oldest first</button>
            <button v-on:click="sortNewest" class="btn btn-sort">Newest first</button>
        </div>
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