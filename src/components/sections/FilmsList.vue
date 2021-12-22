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
import dataShared from '../../share/dataShared';

import Card from '../elements/Card.vue';

export default {
    name: 'FilmsList',
    components: {
        Card
    },
    data() {
        return {
            dataShared
        }
    },
    computed: {
        filmsOrderByPopularity() {
            const films = this.dataShared.films;

            return films.sort((a, b) => {
                return b.popularity - a.popularity;
            });
        }
    }
}
</script>

<style>

</style>