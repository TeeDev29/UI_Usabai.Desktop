<template >
    <div class="container-fluid">

        <div class="row">
            <p class="title text-center pb-4 pt-4">Promotion</p>
            <div class="col-12 col-sm-9 col-md-12 col-lg-9 col-xl-9 col-xxl-9 ">

                <carousel :items-to-show="3" :wrapAround="true" :transition="300" class="m-1">
                    <slide v-for="(items, index) in ads" key="index">
                        <!-- {{  slide  }} -->
                        <a v-bind:href="items.urlPromotion">
                            <img v-bind:src="items.imagePromotion" class="ads d-block ">
                        </a>

                    </slide>

                    <template #addons>
                        <navigation />
                        <pagination />
                    </template>
                </carousel>

            </div>
            <div class="col-3 col-sm-3 col-md-3 col-lg-3 col-xl-3 col-xxl-3 containercontent">
                <p class="title2">We are ready <br>Have pomotion</p>
                <p class="title3">Condition</p>
                <p class="content text-justify">
                    It is the last project of Baan Yu Sabai, Hua Talay Zone. There are four roads cut through.
                </p>
            </div>
        </div>

    </div>
</template>
<script>
import axios from "axios";
import 'vue3-carousel/dist/carousel.css';
// https://ismail9k.github.io/vue3-carousel/ lilbary vue3-carousel
import { Carousel, Slide, Pagination, Navigation } from 'vue3-carousel';
export default {
    components: {
        Carousel,
        Slide,
        Pagination,
        Navigation,
    },
    data() {
        return {
            ads: []
        }
    },
    async mounted() {
        await axios.get("https://www.u-sabai.com/api/web2/promotion.php")
            .then((res) => (this.ads = res.data, console.log(res.data)))
    }
}
</script>
<style scoped>
.container-fluid {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    width: 100%;
}

.container {
    width: 100%;
}

.title {
    font-size: 46px;
    text-transform: uppercase;
    font-weight: 600;
}

.title2 {
    font-size: 28px;
    text-transform: uppercase;
    font-weight: 600;
}

.title3 {
    font-size: 18px;
    font-weight: 300;
}

.content {
    width: 60%;
    font-size: 16px;
    font-weight: 200;
}

.ads {
    width: 400px;
    border-radius: 10px;
    height: 480px;
    object-fit: cover;
    padding-left:5px ;
    /* margin-left: 20px; */
    /* max-height: 270px; */
}

.row {
    width: 100%;
}


/* tablet */
@media only screen and (max-width: 820px) {  

    .container-fluid {
        /* display: none; */
        /* background-color: blue; */
        /* height: 40vh; */
        padding: 0%;
        height: calc(100vh - calc(100vh - 100%));
        padding-bottom: 20px;
    }

    .containercontent {
        display: none;
    }

    .container {
        width: 100%;
        padding: 0%;
    }

    .title {
        font-size: 28px;
    }

    .ads {
        width: 250px;
        border-radius: 10px;
        height: 300px;
        /* max-height: 270px; */
    }


}


/* mobile */
@media only screen and (max-width: 600px) {
    .container-fluid {
        /* display: none; */
        /* background-color: blue; */
        /* height: 40vh; */
        padding: 0%;
        height: calc(100vh - calc(100vh - 100%));
    }

    .containercontent {
        display: none;
    }

    .container {
        width: 100%;
        padding: 0%;
    }

    .title {
        font-size: 26px;
    }

    .ads {
        width: 130px;
        border-radius: 10px;
        height: 180px;
        /* max-height: 270px; */
    }

}
</style>