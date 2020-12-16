<template>
  <tr>
    <td>{{ item.name }}</td>
    <td>S{{ item.season }}E{{ item.number }}</td>
    <td>{{ item.airdate }} at {{ item.airtime }}</td>
    <td>
      <router-link
        :to="{ name: 'episode', params: { id: item.id, name: item.name, episode: item.number, season: item.season, summary: item.summary, runtime: item.runtime, more: item.url, airdate: item.airdate, airtime: item.airtime } }"
        class="btn btn-details"
      >
        View details
      </router-link>
    </td>
  </tr>
</template>

<script>
export default {
    name: 'Item',
    props: {
        item: {
            type: Object,
            default: () => ({})
        }
    }
}
</script>

<style scoped>
</style>