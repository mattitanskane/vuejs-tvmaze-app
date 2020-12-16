<template>
    <div>
        <p>This is a single item</p>
        <p>ID: {{item.id}}</p>
        <p>Title: {{item.title}}</p>
    </div>
</template>

<script>
export default {
    name: 'Show',
    props: ['item']
}
</script>

<style scoped>

</style>