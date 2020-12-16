<template>
    <div>
        <h2>Here is a list of shows</h2>
        <div v-bind:key="item.id" v-for="item in items">
            <Show v-bind:item="item" />
        </div>
    </div>
</template>

<script>
import Show from '@/components/Show'
export default {
    name: 'Shows',
    components: {
        Show
    },
    props: ['items']
}
</script>

<style scoped>

</style>