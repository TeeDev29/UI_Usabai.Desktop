<template>
  <div class="container-fluid">
    <nav>
      <ul>
        <li><a href="#sec2">PROMOTION</a></li>
        <li><a href="#sec3">ALLPROJECT</a></li>
        <li><a href="#sec4">REGISTER</a></li>
        <li><a href="#sec5">ABOUT</a></li>
      </ul>
    </nav>
    <div id="carouselExampleControls" class="carousel slide" data-bs-ride="carousel">
      <div class="carousel-inner">
        <div class="carousel-item" v-for="(items, index) in banner" :class="{ active: index == 0 }">
          <img v-bind:src="items.pathImage" class="imgitem d-block w-100" alt="...">
        </div>
      </div>
      <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleControls"
        data-bs-slide="prev">
        <span class="carousel-control-prev-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Previous</span>
      </button>
      <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleControls"
        data-bs-slide="next">
        <span class="carousel-control-next-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Next</span>
      </button>

    </div>

  </div>




</template>

<script>
import axios from "axios";
export default {
  name: 'HelloWorld',
  data() {
    return {
      banner: []
    }

  },
  async mounted() {
    await axios.get("https://www.u-sabai.com/api/web2/coveweb.php")
      .then((res) => (this.banner = res.data, console.log(res.data)))
  }

}
</script>

<style scoped>
.container-fluid {

  padding: 0;
}

.carousel-inner {
  /* max-height: 940px; */

  height: 100vh;

  width: 100%;
}

/* #carouselExampleControls{
  max-height:300px ;
} */
h3 {
  margin: 40px 0 0;
}

ul {
  list-style-type: none;
  padding: 0;
  margin-bottom: 0px;
}

li {
  display: inline-block;
  margin: 0 10px;
}

nav {
  margin-left: 50%;
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



 /* tablet */
@media only screen and (max-width: 820px) {  
  .carousel-inner {
    background-color: rgb(27, 27, 27);
    height: 50vh;
    /* height: calc(100vh - calc(100vh - 100%)); */
  }

  .imgitem {
    width: 100%;
    height: 50vh;
    object-fit: cover;
  }

  nav {
  margin-left: 40%;
  padding: 14px;

}

nav a {
  /* color: #002855; */
  font-weight: 500;
  font-size: 14px;
}

nav a.router-link-exact-active {
  color: #002855;
}

ul {
  margin-bottom: 0px;
}

}


/* mobile */
@media only screen and (max-width: 600px) {
  .carousel-inner {
    background-color: blue;
    height: 40vh;
    /* height: calc(100vh - calc(100vh - 100%)); */
  }

  .imgitem {
    width: 100%;
    height: 40vh;
    object-fit: cover;
  }

  nav {
    display: none;
  }
}
</style>
