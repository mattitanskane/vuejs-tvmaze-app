<template>
  <article class="home">
    <h1>{{ $route.params.name }}</h1>
    <p>S{{ $route.params.season }}E{{ $route.params.episode }}: Aired on {{ $route.params.airdate }} at {{ $route.params.airtime }}</p>
    <p>Runtime: {{ $route.params.runtime }} minutes</p>
    <a
      :href="$route.params.more"
      target="_blank"
    >
      More info at tvmaze.com
    </a>
    <h2>Episode summary</h2>
    <p v-html="$route.params.summary" />
  </article>
</template>

<script>
// @ is an alias to /src
export default {
    name: 'Details'
}
</script>
