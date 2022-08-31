<template>
    <div class="container-fluid mt-5  pt-5 pb-5">
        <div class="container">
            <p class="title">can your <span>choore</span></p>
        </div>
        <div class="row">
            <div class="col ">
                <div id="carouselExampleControls3" class="carousel slide" data-bs-ride="carousel">
                    <div class="carousel-inner">
                        <div class="carousel-item active">
                            <div class="container d-flex justify-content-center">
                                <cardpj />
                            </div>
                        </div>
                        <div class="carousel-item">
                            <div class="container d-flex justify-content-center">
                                <cardpj />
                            </div>
                        </div>
                        <div class="carousel-item">
                            <div class="container d-flex justify-content-center">
                                <cardpj />
                            </div>
                        </div>
                    </div>
                    <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleControls3"
                        data-bs-slide="prev">
                        <span class="carousel-control-prev-icon" aria-hidden="true"></span>
                        <span class="visually-hidden">Previous</span>
                    </button>
                    <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleControls3"
                        data-bs-slide="next">
                        <span class="carousel-control-next-icon" aria-hidden="true"></span>
                        <span class="visually-hidden">Next</span>
                    </button>
                </div>
            </div>
        </div>

        <!-- <div class="container mt-3">
            <div class="row mt-5">
                <div class="col-6">
                    <p class="zone">JOHO ZONE</p>
                    <img class="logopj" src="@/assets/ESTELLA.png">
                    <img class="logopj" src="@/assets/ESTELLA.png">
                    <img class="logopj" src="@/assets/Ultima.png">
                </div>
                <div class="col-6">
                    <p class="zone">HUA TALAY ZONE</p>
                    <img class="logopj" src="@/assets/ESTELLA.png">
                    <img class="logopj" src="@/assets/ESTELLA.png">
                    <img class="logopj" src="@/assets/Ultima.png">
                </div>
            </div>
        </div> -->


    </div>
</template>
<script>
import cardpj from '@/widgets/cardpj.vue'
export default {
    components: {
        cardpj
    }
}
</script>

<style scoped>
.container-fluid {
    height: 100vh;
    width: 100%;
    /* display: flex; */
}

.zone {
    color: aliceblue;
    text-transform: uppercase;
    font-size: 36px;
}

/* .logopj{
    margin-left: 10px;
    width: 80px;
    transition: 0.5s;
    cursor: pointer;
}

.logopj:hover{
    transform: scale(1.1);
} */

.carousel-control-prev-icon {
    background-color: rgb(0, 0, 0);
}

.carousel-control-next-icon {
    background-color: rgb(0, 0, 0);
}

.container-fluid {
    background-color: #272727;
    /* box-shadow: 0px 0px 15px #e3e3e3; */
    /* border-radius: 10px; */
}

.title {
    color: aliceblue;
    text-transform: uppercase;
    font-size: 36px;
}

.title span {
    /* color: aliceblue;
    text-transform: uppercase;
    font-size: 36px; */
    font-size: 48px;
    font-weight: 500;
    background: -webkit-linear-gradient(180deg, #F7BA2C 0%, #F36E59 40.98%, #F13C77 68.17%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
}
</style>