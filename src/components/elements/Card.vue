<template>
  <div>
    <h3>{{info.title}}</h3>
    <h4>{{info.original_title}}</h4>
    <div>{{info.original_language}}</div>
    <div>{{info.vote_average}}</div>
    <h2>{{info.popularity}}</h2>
  </div>
</template>

<script>
export default {
    name: 'Card',
    props: {
      info: Object
    }
}
</script>

<style>

</style>