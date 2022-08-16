<template>
  <div>
    <!-- <img alt="Vue logo" src="../assets/logo.png"> -->
    <!-- msg="Welcome to Your Vue.js App" -->
    <HelloWorld />
    <introview />
    <promotionview />
    <showpropjview />

  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/Banner.vue'
import introview from '@/components/Intro.vue'
import promotionview from '@/components/Promotion.vue'
import showpropjview from '@/components/showcardpj.vue'
export default {
  name: 'HomeView',
  components: {
    HelloWorld,
    introview,
    promotionview,
    showpropjview
  }
}
</script>
