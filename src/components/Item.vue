<template>
    <tr>
        <td>{{item.name}}</td>
        <td>S{{item.season}}E{{item.number}}</td>
        <td>{{item.airdate}} at {{item.airtime}}</td>
        <td><button class="btn btn-view-details">View details</button></td>
    </tr>
</template>

<script>
export default {
    name: 'Item',
    props: ['item']
}
</script>

<style scoped>
    .btn-view-details {
        display: none;
    }
    tr:hover .btn-view-details {
        display: block;
    }
</style>