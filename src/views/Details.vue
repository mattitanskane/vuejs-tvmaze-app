<template>
  <div class="home">
    <Items />
  </div>
</template>

<script>
// @ is an alias to /src
import Items from '@/components/Items'

export default {
    name: 'Home',
    components: {
        Items
    }
}
</script>
