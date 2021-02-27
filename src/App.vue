<template>
  <div id="app">
    <NavbarMenu />
    <Events/>
    <Footer />
  </div>
</template>

<script>
import Events from './components/Events.vue'
import NavbarMenu from './components/NavbarMenu.vue'
import Footer from './components/Footer.vue'
export default {
  name: 'App',
  components: {
    Events,
    NavbarMenu,
    Footer
  }
}
</script>

<style>
#app {
background:#fff;
}
</style>
