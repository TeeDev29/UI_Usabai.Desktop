<template>
  <!-- <img alt="Vue logo" src="../assets/logo.png"> -->
  <!-- msg="Welcome to Your Vue.js App" -->

  <HelloWorld />
  <introview />
  <promotionview id="sec2" />
  <!-- <showpropjview /> -->
  
  <dreamhouseview />
   <allprojectview id="sec3"/>
  <!-- <mapview /> -->
  <nearyview />
 
  <registerview id="sec4"/>

  <serviceview id="sec5" />

</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/Banner.vue'
import introview from '@/components/Intro.vue'
import promotionview from '@/components/Promotion.vue'
import showpropjview from '@/components/showcardpj.vue'
import dreamhouseview from '@/components/dreamhouse.vue'
import mapview from '@/components/map.vue'
import nearyview from '@/components/locationneary.vue'
import showhomeview from '@/components/showhome.vue'
import allprojectview from '@/components/allproject.vue'
import serviceview from '@/components/serviceview.vue'
import registerview from '@/components/register.vue'
export default {
  name: 'HomeView',
  components: {
    HelloWorld,
    introview,
    promotionview,
    showpropjview,
    dreamhouseview,
    mapview,
    nearyview,
    showhomeview,
    allprojectview,
    serviceview,registerview

  },

}
</script>

<style scoped>
</style>

