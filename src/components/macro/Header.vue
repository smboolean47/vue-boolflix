<template>
  <header>
      <div class="search-bar">
          <form @submit.prevent="searching">
            <input v-model="textToSearch" type="text">
            <button>Cerca</button>
          </form>
      </div>
  </header>
</template>

<script>
import axios from 'axios';
import dataShared from '../../share/dataShared';

export default {
    name: 'Header',
    data() {
        return {
            dataShared,
            textToSearch: ""
        }
    },
    methods: {
    searching() {
      // Films
      axios.get("https://api.themoviedb.org/3/search/movie/", {
        params: {
          api_key: 'e99307154c6dfb0b4750f6603256716d',
          language: 'it-IT',
          query: this.textToSearch
        }
      })
      .then( (response) => {
        this.dataShared.films = response.data.results;
      })
      .catch( (error) => { console.log(error) } );
      
      // Series
      axios.get("https://api.themoviedb.org/3/search/tv/", {
        params: {
          api_key: 'e99307154c6dfb0b4750f6603256716d',
          language: 'it-IT',
          query: this.textToSearch
        }
      })
      .then( (response) => {
        this.dataShared.series = response.data.results;
      })
      .catch( (error) => { console.log(error) } );
    }
  }
}
</script>

<style>

</style>