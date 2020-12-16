<template>
  <div class="home">
    <Tools v-on:filter-items="filterItems" v-on:sort-items="sortItems" />
    <Items v-bind:items="filteredItems"/>
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
    created() {
        axios.get('http://api.tvmaze.com/shows/3474/episodes')
            .then(res => this.items = res.data)
            .catch(err => console.log(err));
    },
    methods: {
        filterItems(search) {
            console.log(search)
            this.search = search
        },
        sortItems() {

        }
    },
    computed: {
        filteredItems: function() {
            console.log(this.items)
            return this.items.filter(item => {
                return item.name.toLowerCase().match(this.search)
            })
        }
    }
}
</script>


<style>
    html {
    box-sizing: border-box;
    font-size: 16px;
    }

    *, *:before, *:after {
    box-sizing: inherit;
    }

    body, h1, h2, h3, h4, h5, h6, p, ol, ul {
    margin: 0;
    padding: 0;
    font-weight: normal;
    }

    ol, ul {
    list-style: none;
    }

    img {
    max-width: 100%;
    height: auto;
    }
    .btn {
        text-transform: uppercase
    }
</style>
