<template>
  <div id="app">
    <Header />
    <Jumbotron />
    <Main />
    <Footer />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Main from './components/Main.vue'
import Footer from './components/Footer.vue'
import Jumbotron from "@/components/jumbotron.vue"
export default {
  name: 'App',
  components: {
    Header,
    Main,
    Footer,
    Jumbotron
  }
}
</script>

<style lang="scss">
@import "@/style/generals.scss";
@import "@/style/vars.scss"
</style>
