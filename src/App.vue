<template>
  <div id="app">
    <Header />
    <FirstSection />
    <ShortenInput />
    <AdvSta />
    <Cta />
    <Footer />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import FirstSection from './components/FirstSection.vue'
import ShortenInput from './components/ShortenInput.vue'
import AdvSta from './components/AdvSta.vue'
import Cta from './components/Cta.vue'
import Footer from './components/Footer.vue'

export default {
  name: 'App',
  components: {
    Header,
    FirstSection,
    ShortenInput,
    AdvSta,
    Cta,
    Footer
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@500;700&display=swap');

#app {
  font-family: 'Poppins';
  font-weight: 500;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  width: 100%;
  margin: 0 auto;
}
</style>
