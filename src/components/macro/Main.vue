<template>
  <main>
    <FilmsList :films="films"/>
  </main>
</template>

<script>
import FilmsList from '../sections/FilmsList.vue';

export default {
    name: 'Main',
    components: {
        FilmsList
    },
    props: {
        films: Array
    }
}
</script>

<style>

</style>