<template>
    <table class="table">
        <thead>
            <th>Name</th>
            <th>Number</th>
            <th>Aired</th>
            <th></th>
        </thead>
        <tbody>
            <Item v-for="(item, index) in items" v-bind:item="item" v-bind:index="index" v-bind:key="item.id" class="row" />
        </tbody>
    </table>
</template>

<script>
import Item from '@/components/Item'
export default {
    name: 'Items',
    components: {
        Item
    },
    props: ['items']
}
</script>

<style scoped>

</style>