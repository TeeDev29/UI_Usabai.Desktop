<template>
    <div class="container-fluid p-5">
        <p class="title">LOCATION NEARY</p>
        <div class="row">
            <div class="col-12 col-sm-6 col-md-6 col-lg-6 col-xl-6 col-xxl-6">

                <div class="row">
                    <div class="col-6 mt-3" v-for="(items, index) in imgneary" :key="index">
                        <div class="card">
                            <img
                               v-bind:src="items.urlImage">
                        </div>
                    </div>
                </div>
            </div>
            <div class="col-12 col-sm-6 col-md-6 col-lg-6 col-xl-6 col-xxl-6">
                <div class="card2 mt-3">
                    <img
                        src="@/assets/neary.jpeg">
                </div>
            </div>
        </div>
    </div>
</template>
<script>
    import axios from "axios";
export default {
    data(){
        return {
            imgneary:[]
        }
    },
   async mounted(){
       await axios.get("https://www.u-sabai.com/api/web2/locationneary.php")
        .then((res)=>(this.imgneary=res.data))
    }
}
</script>

<style scoped>
.container-fluid {
    height: 100vh;
    width: 100%;
    /* display: flex; */
}


.title {
    font-size: 36px;
}

.card {
    width: 100%;
    height: 40vh;
    object-fit: cover;
}

.card img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}

.card2 {
    width: 100%;
    height: 82vh;
    object-fit: cover;
}

.card2 img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}



@media only screen and (max-width: 820px) {


    .container-fluid {
        width: 100%;
        /* height: 40vh; */
        height: calc(100vh - calc(100vh - 100%));
    }
    .title {
    font-size: 28px;
    text-align: center;
}

    .card {
    width: 100%;
    height: 14vh;
    object-fit: cover;
}

.card img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}

.card2 {
    width: 100%;
    height: 29vh;
    object-fit: cover;
}

.card2 img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}


}

@media only screen and (max-width: 600px) {
    .container-fluid {
        width: 100%;
        /* height: 40vh; */
        height: calc(100vh - calc(100vh - 100%));
    }
    .title {
    font-size: 26px;
    text-align: center;
}

    .card {
    width: 100%;
    height: 15vh;
    object-fit: cover;
}

.card img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}

.card2 {
    width: 100%;
    height: 20vh;
    object-fit: cover;
}

.card2 img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}


}
</style>