<template>
    <div class="container-fluid">
        <div class="row">
            <div class="col-12 col-sm-6 col-md-6 col-lg-6 col-xl-6 col-xxl-6 p-0">
                <div class="container p-0">
                    <img class="imghouse" v-bind:src="dream.urlImage" />
                </div>
            </div>
            <div class="col-12 col-sm-6 col-md-6 col-lg-6 col-xl-6 col-xxl-6 content">
                <!-- <div class="container"> -->
                <p class="mt-2">{{  dream.textTitle  }}</p>
                <div class="container">


                    <lottie-player src="https://assets10.lottiefiles.com/packages/lf20_0apkn3k1.json"
                        background="transparent" speed="2"  loop autoplay>
                    </lottie-player>
                </div> <!-- </div> -->
            </div>
        </div>
    </div>
</template>
<script>
import axios from "axios";
export default {
    data() {
        return {
            dream: []
        }
    },
    async mounted() {
        await axios.get("https://www.u-sabai.com/api/web2/suptitle.php")
            .then((res) => (this.dream = res.data[0], console.log(res.data[0])))
    }
}
</script>
<style scoped>
.container-fluid {

    height: 100vh;
    width: 100%;
    display: flex;

}


.cat {
    width: 100%;
}

.row {
    height: 100%;
}

.imghouse {
    width: 100%;
    min-height: 100vh;
    box-shadow: inset 0px 0px 10px rgba(0, 0, 0, 0.327);
}

.content {
    background-color: #272727;
}

.container {
    display: flex;
    height: 50%;
    position: relative;
}

lottie-player {
    align-self: flex-end;
    position: relative;
    width: 500;
     height: 300px;
}

.content p {
    color: aliceblue;
    text-transform: uppercase;
    font-size: 100px;
    font-weight: 500;
    margin: 0;
}

@media only screen and (max-width: 820px) {

    .container-fluid {
        /* display: none; */
        /* height: 40vh; */
        height: calc(100vh - calc(100vh - 100%));
        /* min-height: 32vh; */
    }

    .imghouse {

        min-height: 40vh;
        object-fit: cover;
    }

    .content p {
    color: aliceblue;
    text-transform: uppercase;
    font-size: 50px;
    font-weight: 500;
    margin: 0;
}

lottie-player {
    align-self: flex-end;
    position: relative;
    width: 500;
    height: 280px;

}

}


@media only screen and (max-width: 600px) {
    .container-fluid {
        /* display: none; */
        /* height: 40vh; */
        height: calc(100vh - calc(100vh - 100%));
    }

    .imghouse {

        min-height: 32vh;
        object-fit: cover;
    }

    .content p {
    color: aliceblue;
    text-transform: uppercase;
    font-size: 58px;
    font-weight: 500;
    margin: 0;
}

lottie-player {
    align-self: flex-end;
    position: relative;
    width: 500;
     height: 250px;
}

}
</style>