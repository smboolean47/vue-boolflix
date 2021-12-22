<template>
  <main>
    <FilmsList :films="films"/>
    <SeriesList :series="series"/>
  </main>
</template>

<script>
import FilmsList from '../sections/FilmsList.vue';
import SeriesList from '../sections/SeriesList.vue';

export default {
    name: 'Main',
    components: {
      FilmsList,
      SeriesList
    },
    props: {
      films: Array,
      series: Array
    }
}
</script>

<style>

</style>