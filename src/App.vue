<template>
  <div id="app">
    <router-view/>
    <Footer />
  </div>
</template>

<script>
import Footer from '@/components/Footer'

export default {
  name: 'App',
  components: {
    Footer
  }
}
</script>

<style>
body {
  background-color: #333;
  font-family: 'Roboto', sans-serif;
}
</style>
