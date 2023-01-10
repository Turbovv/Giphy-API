<template>
    <div class="gif" :style="`background-image: url(${gif.images.original.url})`">
    <input ref="url" readonly type="text" :value="gif.images.original.url" style="flex: 1">
    <button @click="copyUrl()">Copy</button>
    </div>
</template>

<script>
export default {
    name:"gifComp",
    props: {
        gif: Object 
    },
    methods: {
        copyUrl() {
            this.$refs.url.select();
            this.$refs.url.setSelectionRange(0, 99999);
            document.execCommand('copy')
            this.$refs.url.value = 'Copied!!!'
        }
    }
}
</script>

<style scoped>
.gif {
  width: 240px;
  height: 240px;
  margin-bottom: 20px;
  display: inline-flex;
  justify-content: center;
  align-items: flex-end;
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
}
</style>