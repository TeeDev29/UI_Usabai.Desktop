<template>
    <div class="container-fluid p-0">
        <img src="@/assets/404.jpeg">
        <div class="con m-5">
            <p class="title">404</p>
            <p class="title2">The web page is not available at this time.</p>
            <p class="title3">sorry for the inconvenience.</p>
            <button type="button" class="btn btn-light">back to home page</button>
        </div>
    </div>
</template>

<script>
export default {

}
</script>

<style scoped>
    .container-fluid{
      display: flex;
    }

img {

    width: 100%;
    height: 100vh;
}

.title {
    font-size: 120px;
    font-weight: 600;
}
.title2{
    font-size: 22px;
}

.title3{
    font-size: 22px;
}

.con{
    position: absolute;
}


/* phone(phones, 600px and down) */
@media only screen and (max-width: 600px) {
 

  img {

width: 100%;
height: 80vh;
object-fit: cover;
    /* height: calc(100vh - calc(100vh - 100%)); */
}

.title2{
    font-size: 16px;
}

.title3{
    font-size: 16px;
}

}

</style>