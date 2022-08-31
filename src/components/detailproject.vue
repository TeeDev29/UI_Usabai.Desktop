<template>
    <div class="container-fluid p-0">
        <section class="s1">
            <img class="imgbanner" v-bind:src="imgbanner1">
            <img class="logo" v-bind:src="location.imageProject">
        </section>

        <section>
            <div class="container">
                <!-- <p class="title1 text-center mt-5">estella</p> -->
                <div class="row">
                    <div class="col-12 d-flex justify-content-center">
                        <div class="card">
                            <div class="col-12 bottomcontent text-end mt-5 mb-3">

                                <div> <span class="loandpititle ">Location :</span> 
                                <span class="location" v-if="location.zoneID === '2'">Hua Talay</span>
                                <span class="location" v-else>JOHO</span>
                                </div>
                                <!-- <span class="loandpititle">Starting price :</span> <span>2,000,000 THB</span> -->
                            </div>
                            <div class="imgproject">
                                <img  v-bind:src="illustration1">
                            </div>
                            <div class="body">
                                <div class="row">
                                    <div class="col-12">
                                        <span class="typetitle">Type of house :</span><span class="hastax">&nbsp;#single
                                            storey house
                                            &nbsp;{{concpet.detail}}</span>
                                        <p class="concepttitle">Concept :</p>
                                        <p class="content">{{concpet.concept}}</p>
                                    </div>
                                    <div class="col-12 bottomcontent text-end">
                                        <!-- <span class="loandpititle">Location :</span> <span>Hua Talay</span> &nbsp; -->
                                        <span class="loandpititle2">Starting price :</span> <span
                                            class="location2">{{concpet.price}}&nbsp;M/THB</span>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>

                </div>
            </div>

        </section>

        <section>
            <div class="imgproject">
                <div class="container">
                    <img v-bind:src="illustration2">
                    <div class="description1 ">{{description.description1}}</div>
                </div>
            </div>
        </section>

        <section>
            <div class="imgproject">
                <div class="container-fluid">
                    <img v-bind:src="illustration3" alt="">
                </div>
            </div>
              <!-- <div class="container"><div class="description1 m-3">{{description.description2}}</div></div> -->
        </section>


        <section>
            <div class="container">
                <p class="alablumtitle text-center mt-5 mb-5">-U-sabai the beginning of a good life.-</p>
                <div class="row">
                    <div class="col-6 col-sm-4 col-md-4 col-lg-4 col-xl-4 col-xxl-4 mt-4" v-for="(items, index) in album" key="index">
                        <img class="itemimg"
                           v-bind:src="items.pathfile"
                            >
                    </div>
                 
                </div>
               <div class="descriptionend mt-5 text-center">
                <span><p>-&nbsp;Because every homeowner is a Member of our family&nbsp;-</p></span>
               </div>
            </div>
        </section>
        <section class="mt-5">
            <registerview />
        </section>

    </div>
</template>
<script>
import registerview from '@/components/register.vue'
import axios from "axios";
export default {
    components: {
        registerview
    },
    data(){
        return {


            album:[],
            concpet:[],
            location:[],
            description:[],
            
            imgbanner1:'',
            illustration1:'',
            illustration2:'',
            illustration3:'',

        }
    },methods: {
        async showdata() {
            
            await axios.get("https://www.u-sabai.com/api/web2/homedetail.php?id=" + this.$route.params.id)
                .then((res) => (
                    this.imgbanner1 = res.data.image[0].pathfile,
                    this.illustration1 = res.data.image[1].pathfile,
                    this.illustration2 = res.data.image[2].pathfile,
                    this.illustration3 = res.data.image[3].pathfile
                    ));
                // console.log(this.imgbanner1);
                // console.log(this.illustration1);
                // console.log(this.illustration2);
                // console.log(this.illustration3);
                // console.log("cattttttttttttttttttttttttttttttttttt");
                // console.log(this.$route.params.id);
           
        }
    },

   async mounted(){

        if(this.$route.params.id== null){
            this.$router.push({name:"home"});
        }

        await axios.get("https://www.u-sabai.com/api/web2/homedetail.php?id="+this.$route.params.id)
        .then((res) => (
         this.album=res.data.image 
        ,this.concpet=res.data.concpet[0]
        ,this.location= res.data.projectdata[0]
        ,this.description = res.data.description[0]
        ))

        if(this.description == null){
            this.$router.push({name:"error"});
        }

        this.showdata() 
    }
}
</script>
<style scoped>
.s1 {
    display: flex;
    height: 100vh;
    width: 100%;
}

.imgbanner {
    filter: brightness(.80);
    width: 100%;
    /* border-radius: 0px 0px 400px 0px; */
}

.logo {
    position: absolute;
    align-self: center;
    left: 45%;
    align-items: center;
    filter: drop-shadow(0px 4px 4px rgba(0, 0, 0, 0.799));
    background-color: aliceblue;
    padding: 10px;
    border-radius: 50%;
}

.title1 {
    font-weight: 600;
    text-transform: uppercase;
    font-size: 48px;
}



.card {
    width: 100%;
    margin-top: 20px;
    border: none;
}

.imgproject img {
    width: 100%;
}

.title img {
    border-radius: 10px 0px 10px 0px;

    background-color: rgb(255, 255, 255);
    width: 60px;
    height: 60px;
}

.typetitle {
    font-size: 18px;
    font-weight: 200;
    color: rgb(165, 165, 165)
}

.hastax {
    font-weight: 400;
}

.concepttitle {
    font-size: 16px;
    font-weight: 200;
    color: rgb(165, 165, 165);
    margin-top: 10px;
    margin-bottom: 0;
}

.content {
    font-size: 16px;
    font-weight: 300;
    text-align: justify;
}

.description1 {
    margin: 16px;
    font-size: 16px;
    font-weight: 300;
    text-align: justify;
}
.descriptionend{
     text-transform: uppercase;
    color: #a1a1a1;
}
.loandpititle {
    font-size: 36px;
    text-transform: uppercase;
    font-weight: 200;
    color: rgb(165, 165, 165);
    margin-top: 10px;
    margin-bottom: 0;

}

.location {
    font-size: 36px;
    text-transform: uppercase;
    font-weight: 600;
}

.loandpititle2 {
    font-size: 24px;
    text-transform: uppercase;
    font-weight: 200;
    color: rgb(165, 165, 165);
    margin-top: 10px;
    margin-bottom: 0;

}

.location2 {
    font-size: 24px;
    text-transform: uppercase;
    font-weight: 600;
}

.bottomcontent {
    align-self: flex-end;
}


.crop {
    background-color: #a2d2ff;
    border-radius: 50px;
}

.crop2 {

    border-radius: 50px;
}

.itemimg {
    width: 400px;
    height: 400px;
    transition: 0.5s;
    object-fit: cover;
}

.itemimg:hover {
     /* object-fit: scale-down; */

    transform: scale(1.05);
    box-shadow: 0px 4px 10px #a1a1a1;

}

.alablumtitle {
    text-transform: uppercase;
    color: #a1a1a1;
}

.body{
    padding: 24px;

}
@media only screen and (max-width: 820px) {


    .s1 {
   
   height: 50vh;
   width: 100%;
}

.imgbanner {
   object-fit: cover;
}

.logo {
   width: 80px;
   left: 47%;
   align-items: center;
   /* padding: 10px; */
   border-radius: 50%;
}

.loandpititle {
   font-size: 20px;
 

}

.location {
   font-size: 26px;
 
}

.typetitle {
   font-size: 14px;
   font-weight: 200;
   color: rgb(165, 165, 165)
}

.hastax {
   font-size: 14px;
   font-weight: 400;
}


.concepttitle {
   font-size: 14px;
  margin-top: 0px;
}

.content {
   font-size: 14px;
   font-weight: 300;
   text-align: justify;
}
.body{
   padding: 5px 0px;
   
}


.loandpititle2 {
   font-size: 20px;
 

}

.location2 {
   font-size: 26px;

}
.bottomcontent {
   margin-top: 20px;
   align-self: flex-end;
}

.description1 {
   margin: 16px 0px;
   font-size: 14px;
   font-weight: 300;
   text-align: justify;
}

.alablumtitle {
   font-size: 12px;
}

.descriptionend{
   font-size: 12px;
}

.itemimg {
   width: 220px;
   height: 160px;
   object-fit: cover;
}


}


@media only screen and (max-width: 600px) {
    .s1 {
   
    height: 40vh;
    width: 100%;
}

.imgbanner {
    object-fit: cover;
}

.logo {
    width: 80px;
    left: 40%;
    align-items: center;
    /* padding: 10px; */
    border-radius: 50%;
}

.loandpititle {
    font-size: 20px;
  

}

.location {
    font-size: 26px;
  
}

.typetitle {
    font-size: 14px;
    font-weight: 200;
    color: rgb(165, 165, 165)
}

.hastax {
    font-size: 14px;
    font-weight: 400;
}


.concepttitle {
    font-size: 14px;
   margin-top: 0px;
}

.content {
    font-size: 14px;
    font-weight: 300;
    text-align: justify;
}
.body{
    padding: 5px 0px;
    
}


.loandpititle2 {
    font-size: 20px;
  

}

.location2 {
    font-size: 26px;
 
}
.bottomcontent {
    margin-top: 20px;
    align-self: flex-end;
}

.description1 {
    margin: 16px 0px;
    font-size: 14px;
    font-weight: 300;
    text-align: justify;
}

.alablumtitle {
    font-size: 12px;
}

 .descriptionend{
    font-size: 12px;
}

.itemimg {
    width: 180px;
    height: 140px;
    object-fit: cover;
}

}

</style>