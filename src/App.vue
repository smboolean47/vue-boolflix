<template>
  <div id="app">
    <Header @search="searching"/>
    <Main :series="series" :films="films"/>
    <Footer/>
  </div>
</template>

<script>
import axios from 'axios';

import Header from './components/macro/Header.vue';
import Main from './components/macro/Main.vue';
import Footer from './components/macro/Footer.vue';

export default {
  name: 'App',
  components: {
    Header,
    Main,
    Footer
  },
  data() {
    return {
      films: [],
      series: []
    }
  },
  methods: {
    searching(payload) {
      // Films
      axios.get("https://api.themoviedb.org/3/search/movie/", {
        params: {
          api_key: 'e99307154c6dfb0b4750f6603256716d',
          language: 'it-IT',
          query: payload
        }
      })
      .then( (response) => {
        this.films = response.data.results;
      })
      .catch( (error) => { console.log(error) } );
      
      // Series
      axios.get("https://api.themoviedb.org/3/search/tv/", {
        params: {
          api_key: 'e99307154c6dfb0b4750f6603256716d',
          language: 'it-IT',
          query: payload
        }
      })
      .then( (response) => {
        this.series = response.data.results;
      })
      .catch( (error) => { console.log(error) } );
    }
  }
}
</script>

<style lang="scss">

</style>
