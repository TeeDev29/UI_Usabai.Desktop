<template>
    <div class="container-fluid">
        <!-- <div class="container"> -->
                
        <div class="row rowintro">
            <div class="col-6 col-sm-6 col-md-6 col-lg-6 col-xl-6 col-xxl-6 text-start">
                 <h1 class="title1">{{obj.textleft}}</h1>
                <img class="imgtitle mt-5"
                   v-bind:src="obj.image1" />
            </div>
            <div class="col-6 col-sm-6 col-md-6 col-lg-6 col-xl-6 col-xxl-6 text-start">
                <img class="imgtitle"
                v-bind:src="obj.image2"/>
                <h1 class="title1 mt-5">{{obj.textRigh}}</h1>
                
            </div>
        </div>

        <!-- </div> -->
    </div>
</template>

<script>
   import axios from "axios";
   export default {

    data(){
        return{
            obj:[]
        }
    },
    mounted(){
        axios.get("https://www.u-sabai.com/api/web2/sectiontwo.php")
        .then((res)=>(this.obj=res.data[0]))
    }

   }

</script>

<style scoped>
.container-fluid {
    background-color: #272727;
    color: white;
    height: 100vh;
  width: 100%;
  display: flex;
}

.imgtitle {
    width: 100%;
}

.rowintro{
    padding: 5%;
}


/* tablet */
@media only screen and (max-width: 820px) {  
    .container-fluid  {
    /* background-color: blue; */
    /* height: 40vh; */
    height: calc(100vh - calc(100vh - 100%));
  }
  .imgtitle{
    width: 100%;
    /* height: 40vh; */
    object-fit: cover;
  }
  .title1{
    font-size: 28px;
  }

}

/* mobile */
@media only screen and (max-width: 600px) {
  .container-fluid  {
    /* background-color: blue; */
    /* height: 40vh; */
    height: calc(100vh - calc(100vh - 100%));
  }
  .imgtitle{
    width: 100%;
    /* height: 40vh; */
    object-fit: cover;
  }
  .title1{
    font-size: 26px;
  }
}


</style>