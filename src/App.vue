<template>
  <div class="container">
    <nav>
      <router-link to="/"><img class="logo" alt="Vue logo" src="@/assets/logousabai.png">Home</router-link> |
      <router-link to="/about">About</router-link>
    </nav>
  </div>
  <router-view />
</template>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.logo{
  width: 45px;
  height: 45px;
  margin-right: 10px;
}
.container{
  background-color: #2c3e50;
}

nav {
    background-color: #000000;
  position: absolute;
  z-index: 1;
  padding: 16px;
  border-radius: 0 0 5px 5px;
  color: aliceblue;
}

nav a {
  font-weight: 500;
  color: #ffffff;
  text-decoration: none;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>
