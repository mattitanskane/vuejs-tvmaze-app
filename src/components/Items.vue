<template>
  <table class="table">
    <thead>
      <th>Name</th>
      <th>Episode number</th>
      <th>Originally aired on</th>
      <th />
    </thead>
    <tbody>
      <Item
        v-for="(item, index) in items"
        :key="item.id"
        :item="item"
        :index="index"
        class="row"
      />
      <tr v-if="items.length == 0">
        <td
          colspan="4"
          class="no-results"
        >
          No matching results.
        </td>
      </tr>
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
    props: {
        items: {
            type: Array,
            default: () => ([])
        }
    }
}
</script>

<style scoped>
    .no-results {
        padding-top: 20px;
    }
</style>