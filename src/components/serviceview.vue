<template>
    <div class="container-fluid text-center">
        <img class="imguta" src="@/assets/uta.png">
        <div class="row mt-5">
            <div class="col-12">
                <p class="title pb-2">our services</p>
            </div>
            <div class="col-12">
                <div class="row ">
                    <div class="col-4 d-flex justify-content-center">
                        <cardservice/>
                    </div>
                     <div class="col-4 d-flex justify-content-center">
                        <cardservice/>
                    </div>
                     <div class="col-4 d-flex justify-content-center">
                        <cardservice/>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
import cardservice from '@/widgets/cardservice.vue'
export default {
    components:{
        cardservice
    }
}
</script>
<style scoped>
.imguta{
    width: 250px ;
}
    .title{
        font-size: 36px;
        text-transform: uppercase;
        font-weight: 600;
    }
</style>