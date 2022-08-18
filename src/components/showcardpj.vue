<template>
    <div class="container-fluid mt-5  pt-5 pb-5">
        <div class="container">
            <p class="title">can your choore</p>
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
                    <button class="carousel-control-prev" type="button"  data-bs-target="#carouselExampleControls3"
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
.carousel-control-prev-icon{
   background-color: rgb(0, 0, 0);
}
.carousel-control-next-icon{
    background-color: rgb(0, 0, 0);
}
.container-fluid {
    background-color: #ffffff;
         /* box-shadow: 0px 0px 15px #e3e3e3; */
        /* border-radius: 10px; */
}
.title {
    text-transform: uppercase;
    font-size: 36px;
}

</style>