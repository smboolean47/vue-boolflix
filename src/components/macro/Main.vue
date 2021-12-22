<template>
  <main>
    <FilmsList/>
    <SeriesList/>
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
    }
}
</script>

<style>

</style>