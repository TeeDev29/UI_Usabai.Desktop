<template >
    <!-- <div class="container-fluid"> -->
    <div class="card ">
        <div class="title text-center">
            <p>contract <br> sale</p>
        </div>
        <div class="imghome">
            <img src="@/assets/homeft.png"/>
        </div>
       
    </div>
    <!-- </div> -->
</template>
<script>
export default {

}
</script>
<style scoped>
.card {
    /* position: relative; */
    border: none;
    width: 80%;
    max-height: 315px;
    min-height: 615px;
    background: linear-gradient(180deg, #DCDEF2 0%, #F3DEE3 100%);
    border-radius: 20px;
    overflow: hidden;
}

.title {
    position: absolute;
    top: 50%;
    left: 50%;
    margin-top: -100px;
    margin-left: -100px;
   
}

.title p {
    font-weight: 600;
    font-size: 36px;
    text-transform: uppercase;
    color: aliceblue;
}

.imghome{
       position: absolute;
       bottom: 0px;
}

.imghome img{
    width: 100%;   
}

</style>