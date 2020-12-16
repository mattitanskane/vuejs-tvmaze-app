<template>
  <div class="home">
    <Tools
      @filter-items="filterItems"
      @sort-alpha="sortAlphabetically"
      @sort-new="sortByNewest"
      @sort-old="sortByOldest"
    />
    <Items :items="filteredItems" />
  </div>
</template>

<script>
import axios from 'axios'

// @ is an alias to /src
import Tools from '@/components/Tools'
import Items from '@/components/Items'

export default {
    name: 'Home',
    components: {
        Items,
        Tools
    },
    data() {
        return {
            items: [],
            search: '',
            sortBy: 0
        }
    },
    computed: {
        filteredItems: function() {
            return this.items.filter(item => {
                return item.name.toLowerCase().match(this.search)
            })
        }
    },
    created() {
        axios.get('http://api.tvmaze.com/shows/3474/episodes')
            .then(res => this.items = res.data)
            .catch(err => console.log(err))
    },
    methods: {
        filterItems(search) {
            this.search = search
        },
        sortAlphabetically() {
            return this.items.sort((a, b) => {
                if (a.name < b.name) { return -1 }
                if (a.name > b.name) { return 1 }
                return 0
            })
        },
        sortByNewest() {
            return this.items.sort((a, b) => {
                const aDate = new Date(a.airstamp)
                const bDate = new Date(b.airstamp)
                return bDate - aDate
            })
        },
        sortByOldest() {
            return this.items.sort((a, b) => {
                const aDate = new Date(a.airstamp)
                const bDate = new Date(b.airstamp)
                return aDate - bDate
            })
        },
    }
}
</script>

<style>
</style>
