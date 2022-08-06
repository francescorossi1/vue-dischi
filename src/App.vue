<template>
  <div>
    <MainHeader @set-option="setSelectedOption" :genres-list="genres" />
    <MainContent :selectedOption="selectedOption" @get-data="getGenre" />
  </div>
</template>

<script>
import MainHeader from './components/MainHeader.vue';
import MainContent from './components/MainContent.vue';

export default {
  name: 'App',
  data() {
    return {
      selectedOption: '',
      genres: []
    }
  },
  methods: {
    setSelectedOption(value) {
      this.selectedOption = value
    }, getGenre(value) {
      this.genres = value
      console.log(value)
    }
  },
  components: {
    MainHeader,
    MainContent
  }
}
</script>

<style lang="scss">
@import './assets/sass/style.scss';

body {
  background-color: #1E2D3B;
}
</style>
