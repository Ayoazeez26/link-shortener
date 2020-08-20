<template>
  <div id="app">
    <Header />
    <FirstSection />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import FirstSection from './components/FirstSection.vue'

export default {
  name: 'App',
  components: {
    Header,
    FirstSection
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
  width: 1280px;
  margin: 0 auto;
}

.cyan {
  color: hsl(180, 66%, 49%);
}

.dark-violet {
  color: hsl(257, 27%, 26%);
}

.red {
  color: hsl(0, 87%, 67%);
}

.gray {
  color: hsl(0, 0%, 75%)
}

.grayish-violet {
  color: hsl(257, 7%, 63%);
}

.very-dark-blue {
  color: hsl(255, 11%, 22%);
}

.very-dark-violet {
  color: hsl(260, 8%, 14%);
}

@media screen and (max-width: 1279px) {
    
  #app {
    width: 100%;
  }

}

@media screen and (max-width: 768px) {
    
  #app {
    width: 90%;
  }

}
</style>
