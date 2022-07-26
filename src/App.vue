<template>
  <div>
    <MainHeader />
    <MainContent />
  </div>
</template>

<script>
import MainHeader from './components/MainHeader.vue';
import MainContent from './components/MainContent.vue';

export default {
  name: 'App',
  components: {
    MainHeader,
    MainContent
}
}
</script>

<style lang="scss">
@import './assets/sass/style.scss';

body{
  background-color: #1E2D3B;
}
</style>
