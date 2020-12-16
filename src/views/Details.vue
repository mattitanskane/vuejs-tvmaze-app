<template>
  <div class="home">
    <Shows />
  </div>
</template>

<script>
// @ is an alias to /src
import Shows from '@/components/Shows'

export default {
    name: 'Home',
    components: {
        Shows
    }
}
</script>
