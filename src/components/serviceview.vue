<template>
    <div class="container-fluid p-0 mt-5">

        <!-- <p class="title pb-2 mt-5">Follow us here</p> -->
        <div class="row">
            <div class="col-12 col-sm-6 col-md-6 col-lg-6 col-xl-6 col-xxl-6 p-0">
                <!-- <div class="container p-0"> -->
                <img class="imghouse"
                    src="https://images.unsplash.com/photo-1661565883728-c29018265f32?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2370&q=80" />
                <!-- </div> -->
            </div>
            <div class="col-12 col-sm-6 col-md-6 col-lg-6 col-xl-6 col-xxl-6 p-0">
                <!-- <div class="container"> -->
                <p class="content ps-3">Follow<br>us here</p>
                <div class="row rowso">
                    <!--p-5-->
                    <div class="col-4 p-1">
                        <a href="https://www.facebook.com/usabaigroupkorat">
                            <div class="card text-center">
                                <img src="@/assets/icon/facebook.png"
                                    class="card-img-top center-block d-block mx-auto mt-3">
                                <div class="card-body">
                                    <span class="card-text">
                                        Usabai Group korat
                                    </span>
                                </div>
                            </div>
                        </a>
                    </div>

                    <div class="col-4 p-1">
                        <a href="https://www.facebook.com/usabaihuathalaekorat">
                            <div class="card text-center">
                                <img src="@/assets/icon/facebook.png"
                                    class="card-img-top center-block d-block mx-auto mt-3">
                                <div class="card-body">
                                    <span class="card-text">
                                        บ้านอยู่สบาย - หัวทะเลโคราช
                                    </span>
                                </div>
                            </div>
                        </a>
                    </div>



                    <div class="col-4 p-1">
                        <a href="https://www.instagram.com/u_sabai/">
                            <div class="card text-center">
                                <img src="@/assets/icon/instagram.png"
                                    class="card-img-top center-block d-block mx-auto mt-3">
                                <div class="card-body">
                                    <p class="card-text">u_sabai</p>
                                </div>
                            </div>
                        </a>
                    </div>
                    <div class="col-4 p-1">
                        <a
                            href="https://twitter.com/UsabaiGroup?t=GeKUSwpOF-guMw7x6jGBxA&s=09&fbclid=IwAR1A-kfWaurz7z3saKtCGFL2IcwVXdBm2VTRxJh7zV57zNTFkp07td87X6A">
                            <div class="card text-center">
                                <img src="@/assets/icon/twitter.png"
                                    class="card-img-top center-block d-block mx-auto mt-3">
                                <div class="card-body">
                                    <p class="card-text">@UsabaiGroup
                                    </p>
                                </div>
                            </div>
                        </a>
                    </div>
                    <div class="col-4 p-1">
                        <a href="https://www.tiktok.com/@u_sabai">
                            <div class="card text-center">
                                <img src="@/assets/icon/tik-tok.png"
                                    class="card-img-top center-block d-block mx-auto mt-3">
                                <div class="card-body">
                                    <p class="card-text">u_sabai</p>
                                </div>
                            </div>
                        </a>
                    </div>
                    <div class="col-4 p-1">
                        <a href="https://www.youtube.com/channel/UCeMNYzUaw7bpKlUCkJQBqyQ">
                            <div class="card text-center">
                                <img src="@/assets/icon/youtube.png"
                                    class="card-img-top center-block d-block mx-auto mt-3">
                                <div class="card-body">
                                    <p class="card-text">U-Sabai
                                        Group</p>
                                </div>
                            </div>
                        </a>
                    </div>

                    <div class="col-4 p-1">
                        <a href="https://page.line.me/698wfedw?openQrModal=true">
                            <div class="card text-center">
                                <img src="@/assets/icon/line.png"
                                    class="card-img-top center-block d-block mx-auto mt-3">
                                <div class="card-body">
                                    <p class="card-text">@u_sabai</p>
                                </div>
                            </div>
                        </a>
                    </div>


                </div>

            </div>
        </div>

    </div>
</template>
<script>
import cardservice from '@/widgets/cardservice.vue'
export default {
    components: {
        cardservice
    }
}
</script>
<style scoped>
.container-fluid {
    /* display: flex; */
    height: 100vh;
    width: 100%;
}


/* .card {} */
.card img {
    padding: 10px;
    width: 40%;
}

a {
    font-size: 18px;
    font-weight: 500;
    color: black;
    text-decoration: none;
}

.imguta {
    width: 250px;
}

.title {
    font-size: 36px;
    text-transform: uppercase;
    font-weight: 600;
}

.card {
    border-radius: 20px;
    border: none;
    width: 100%;
    height: 100%;
    background: #fff;
    box-shadow: 0px 0px 10px rgba(204, 204, 204, 0.327);
    cursor: pointer;
}

.rowso {
    padding: 5%;
    margin: 0px;
}

.imghouse {

    width: 100%;
    min-height: 100vh;
    box-shadow: inset 0px 0px 10px rgba(0, 0, 0, 0.327);
}


/* .container {
    display: flex;
    height: 50%;
    position: relative;
} */

.content {

    /* background: linear-gradient(180deg, #DCDEF2 0%, #F3DEE3 100%); */
    color: rgb(0, 0, 0);
    text-transform: uppercase;
    font-size: 100px;
    font-weight: 600;
    margin: 0;
}

@media only screen and (max-width: 820px) {

    .container-fluid {
        /* background-color: blue; */
        /* height: 40vh; */
        /* width: 100%; */
        height: calc(100vh - calc(100vh - 100%));
    }

    .imghouse {
        width: 100%;
        min-height: 50vh;
    }

    .content {
        font-size: 40px;
    }

    .card {
        overflow: hidden;
        width: 110px;
        height: 110px;

    }

    .card img {
        padding: 2px;
        width: 40%;
    }

    .card-text {
        font-size: 8px;
    }


}

@media only screen and (max-width: 600px) {
    .container-fluid {
        /* background-color: blue; */
        /* height: 40vh; */
        /* width: 100%; */
        height: calc(100vh - calc(100vh - 100%));
    }

    .imghouse {
        width: 100%;
        min-height: 50vh;
    }

    .content {
        font-size: 40px;
    }

    .card {
        overflow: hidden;
        width: 110px;
        height: 110px;

    }

    .card img {
        padding: 2px;
        width: 40%;
    }

    .card-text {
        font-size: 8px;
    }
}
</style>