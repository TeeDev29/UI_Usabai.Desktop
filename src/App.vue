<template>
  <div class="container ">
    <nav>
      <router-link to="/"> <img class="logo" alt="Vue logo" v-bind:src=imglogo></router-link> 
      <!-- <router-link to="/about">About</router-link> -->
    </nav>
  </div>
  <router-view />
  <footerview />
</template>

<script>
import footerview from '@/components/footer.vue'
import axios from "axios";

export default {
  components: {
    footerview
  }, data() {
    return {
      imglogo: ""
    }
  }, methods: {
  },
  mounted() {
    axios.get("https://www.u-sabai.com/api/web2/logo.php")
      .then((res) => (this.imglogo = res.data[0].url));
  }
}
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.logo {
  width: 60px;
  height: 60px;
  /* margin-right: 10px; */
}

.container {
  background-color: #2c3e50;
}

nav {
  /* background-color: #000000; */
  background: rgba(173, 173, 173, 0.5);
  backdrop-filter: blur(2px);
  position: absolute;
  z-index: 1;
  padding: 14px;
  border-radius: 0 0 5px 5px;
  color: aliceblue;
}

nav a {
  font-weight: 500;
  color: #ffffff;
  text-decoration: none;
}

nav a.router-link-exact-active {
  color: #002855;
}

@media only screen and (max-width: 820px) {
  .logo {
  width: 45px;
  height: 45px;
  /* margin-right: 10px; */
}
}

@media only screen and (max-width: 600px) {
  .logo {
  width: 45px;
  height: 45px;
  /* margin-right: 10px; */
}
}
</style>
