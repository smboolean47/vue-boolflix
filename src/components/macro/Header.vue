<template>
  <header>
      <div class="search-bar">
          <form @submit.prevent="$emit('search', textToSerach)">
            <input v-model="textToSerach" type="text">
            <button>Cerca</button>
          </form>
      </div>
  </header>
</template>

<script>
export default {
    name: 'Header',
    data() {
        return {
            textToSerach: ""
        }
    }
}
</script>

<style>

</style>