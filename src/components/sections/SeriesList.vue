<template>
  <section>
    <h2>Serie Tv</h2>
    <ul>
        <li v-for="(serie,index) in dataShared.series" :key="index">
            <Card :info="serie"/>
        </li>
    </ul>
  </section>
</template>

<script>
import dataShared from '../../share/dataShared';

import Card from '../elements/Card.vue';

export default {
    name: "SeriesList",
    data() {
        return {
            dataShared
        }
    },
    components: {
        Card
    }
}
</script>

<style>

</style>