<template>
  <div id="app">
    <Header/>
    <Main/>
    <Footer/>
  </div>
</template>

<script>
import Main from "./components/macro/Main.vue"
import Header from "./components/macro/Header.vue"
import Footer from "./components/macro/Footer.vue"

export default {
  name: 'App',
  components: {
    Main,
    Header,
    Footer
  }
}
</script>

<style lang="scss">
@import "./assets/style/global.scss";

  #app{
    background-color: #141414;
  }
</style>
