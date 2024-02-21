<script>
import HeaderComp from './components/Header.vue'
import MainComp from './components/Main.vue'
import FooterComp from './components/Footer.vue'

export default {
  name: 'App',
  components: {
    HeaderComp,
    MainComp,
    FooterComp
  }
};
</script>

<template>
  <HeaderComp class="z-30 w-full sticky top-0"/>
  <MainComp/>
  <FooterComp/>
</template>

<style scoped>

</style>
