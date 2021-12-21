<template>
  <section>
    <h2>Films</h2>
    <ul>
        <li v-for="(film,index) in filmsOrderByPopularity" :key="index">
            <Card :info="film"/>
        </li>
    </ul>
  </section>
</template>

<script>
import Card from '../elements/Card.vue';

export default {
    name: 'FilmsList',
    props: {
        films: Array
    },
    components: {
        Card
    },
    computed: {
        filmsOrderByPopularity() {
            const films = this.films;

            return films.sort((a, b) => {
                return b.popularity - a.popularity;
            });
        }
    }
}
</script>

<style>

</style>