<template>
  <nav>
    <input
      v-model="search"
      type="text"
      placeholder="Search episodes..."
      @input="filterItems"
    >
    <div>
      <p>Sort by</p>
      <button
        class="btn btn-sort"
        @click="sortAlphabetical"
      >
        Name
      </button>
      <button
        class="btn btn-sort"
        @click="sortOldest"
      >
        Oldest first
      </button>
      <button
        class="btn btn-sort"
        @click="sortNewest"
      >
        Newest first
      </button>
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