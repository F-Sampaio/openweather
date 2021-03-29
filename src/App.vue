<template>
    <Search />
</template>

<script>
import Search from './components/Search.vue'
export default {
  name: 'App',
  components: {Search}
}
</script>

<style>
html {
  background: rgb(52,211,153);
  background: linear-gradient(180deg, rgba(52,211,153,1) 0%, rgba(59,130,246,1) 100%);
  min-height: 100%;
  min-width: 100%;
}
</style>
