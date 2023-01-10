<template>
<div id="giflist">
    <GifComp  v-for="gif in gifs" :gif="gif" :key="gif.id" />
</div>
</template>

<script>
import GifComp from './GifComp.vue'
export default {
    name:"GifList",
    components: {
        GifComp
    },
    props: {
        gifs: Array 
    }
}
</script>

<style scoped>
  #gifList {
    margin-top: 20px;
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
  }
</style>