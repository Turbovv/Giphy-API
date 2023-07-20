<template>
 <input placeholder="Type something to search for awesome gifs" v-model="searchWord" @input="onInput">
   </template>
   
   <script>
   
   export default {
    name:"SearchForm",
    data() {
      return {
        searchWord:'',
        timeout: null,
      }
    },
    methods: {
      onInput() {
        clearTimeout(this.timeout);
      this.timeout = setTimeout(() => {
        this.search();
      }, 500)
      },
      search() {
        fetch(`https://api.giphy.com/v1/gifs/search?api_key=j8xGCQElHY1xbE64wNZUoVeMohcYRwb8&q=${this.searchWord}`)
        .then(response => response.json())
        .then(result => {
          this.gifs = result.data
          this.$emit('fetch-gifs', result.data);
          
        })
      }
    },
   }
  
   </script>
   
   <style scoped>
   input {
  padding: 10px 16px;
  border-radius: 4px;
  font-size: 18px;
  border: 2px solid #5f5f5f;
  outline: 0;
  display: block;
  width:50%;
  margin: 0 auto;
}
input:focus {
  border-color: #009ad7;
}

   </style>