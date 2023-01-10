<template>
<SearchForm  @fetch-gifs="onFetch"/>
<GifList :gifs="gifs"/>
</template>

<script>
import SearchForm from './components/SearchForm.vue'
import GifList from './components/GifList.vue'
export default {
  name: 'App',
components: {
  SearchForm,
  GifList
},
data() {
  return {
    gifs: []
  }
},
methods: {
  onFetch(result) {
    this.gifs = result
  }
}
}
</script>

<style>
* {
  box-sizing: border-box;
}
body {
  padding: 50px
}
#app {
  width: 800px;
  margin: 0 auto;
}
</style>
