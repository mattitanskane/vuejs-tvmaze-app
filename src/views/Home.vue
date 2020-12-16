<template>
  <div class="home">
    <Tools v-on:filter-items="filterItems" v-on:sort-items="sortItems" />
    <Shows v-bind:items="items"/>
  </div>
</template>

<script>
// @ is an alias to /src
import Tools from '@/components/Tools'
import Shows from '@/components/Shows'

export default {
    name: 'Home',
    components: {
        Shows,
        Tools
    },
    data() {
        return {
            items: [
                {
                    id: 1,
                    title: "sunt aut facere repellat provident occaecati excepturi optio reprehenderit",
                },
                {
                    id: 2,
                    title: "qui est esse",
                },
                {
                    id: 3,
                    title: "ea molestias quasi exercitationem repellat qui ipsa sit aut",
                }
            ],
            search: '',
            sortBy: 0
        }
    },
    methods: {
        filterItems(search) {
            console.log(search)
        },
        sortItems() {

        }
    },
    computed: {
        filteredItems: function() {
            return true
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
