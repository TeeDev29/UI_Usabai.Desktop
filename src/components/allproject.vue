<template>
    <div class="container-fluid mt-5 p-0">
        <div class="row w-100 ps-4">

            <div class="col-12 p-0">
                <ul class="nav nav-pills mb-3 d-flex justify-content-center" id="pills-tab" role="tablist">
                    <li class="nav-item" role="presentation">
                        <button class="nav-link active" id="pills-home-tab" data-bs-toggle="pill"
                            data-bs-target="#pills-home" type="button" role="tab" aria-controls="pills-home"
                            aria-selected="true">CHOHO</button>
                    </li>
                    <li class="nav-item" role="presentation">
                        <button class="nav-link" id="pills-profile-tab" data-bs-toggle="pill"
                            data-bs-target="#pills-profile" type="button" role="tab" aria-controls="pills-profile"
                            aria-selected="false">HUA THALAE</button>
                    </li>

                </ul>
                <div class="tab-content pb-5" id="pills-tabContent">

                    <!-- JoHo---------------------------------------------------------------- -->
                    <div class="tab-pane fade show active" id="pills-home" role="tabpanel"
                        aria-labelledby="pills-home-tab">
                        <div class="row">
                            <div class="col-12 col-sm-12 col-md-12 col-lg-8 col-xl-8 col-xxl-8 p-2">
                                <div class="col-12">
                                    <div class="scrolling-wrapper row flex-row flex-nowrap pb-4">
                                        <div v-for="(items, index) in datacardJ" :key="index" class="card p-0"
                                            @click="showdata(items)">
                                            <img class="logopj" v-bind:src="items.logo">
                                            <div class="card-body ">
                                                <p class="nameproject">{{  items.project_Name  }}</p>
                                            </div>
                                        </div>
                                    </div>

                                </div>
                                <div class="col-12">
                                    <div class="carddetail mt-3">
                                        <div class="disble" v-show="showimgtitles">
                                            <div class="row">
                                                <div class="col-12 col-sm-12 col-md-12 col-lg-7 col-xl-7 col-xxl-7">
                                                    <img class="showimgdetail p-3"
                                                        src="https://images.unsplash.com/photo-1501183638710-841dd1904471?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80">
                                                </div>
                                                <div
                                                    class="col-12 col-sm-12 col-md-12 col-lg-4 col-xl-4 col-xxl-4 p-0 rowdetail">
                                                    <p class="title1 mt-4">projects</p>
                                                    <p class="title2">CHOHO<br> ZONE.</p>
                                                    <p class="title3">Click on the card<br> above for details.</p>
                                                </div>
                                            </div>
                                        </div>
                                        <div class="row" v-show="showdetail">
                                            <div class="col-12 col-sm-12 col-md-12 col-lg-8 col-xl-8 col-xxl-8">
                                                <img class="showimgdetail p-3" v-for="(items, index) in imgcard"
                                                    :key="index" v-bind:src="items.pathfile"
                                                    v-show:src="index == imgindex">
                                            </div>
                                            <div
                                                class="col-12 col-sm-12 col-md-12 col-lg-4 col-xl-4 col-xxl-4 p-0 rowdetail">
                                                <p class="namecarddetail">{{  detailcard.project_Name  }}</p>

                                                <router-link :to="{ name: 'detail', params: { id: detailcard.id } }">
                                                    <p>Click for more details.</p>
                                                </router-link>

                                                <span class="locationdetail"><i class="fa-solid fa-house"></i>&nbsp;Type
                                                    of house :
                                                    &nbsp; {{  detailcard.detail  }}</span> <br>
                                                <span class="locationdetail"><i class="fa-solid fa-location-dot"></i>
                                                    &nbsp; {{  detailcard.zone  }}</span> <br>

                                                <span class="locationdetail"><i class="fa-solid fa-tags"></i>
                                                    &nbsp; START : {{  detailcard.price  }} M / THB</span>
                                                <p class="concepttitle">Concept :</p>
                                                <p class="content">{{  detailcard.concept  }} </p>
                                                <p>MORE IMAGE</p>
                                                <img class="imgmore" v-for="(items, index) in imgcard" :key="index"
                                                    v-bind:src="items.pathfile" @click="getindeximg(index)">
                                            </div>
                                        </div>
                                    </div>
                                </div>
                            </div>

                            <div class="col-12 col-sm-12 col-md-12 col-lg-4 col-xl-4 col-xxl-4 p-0">
                                <iframe class="map"
                                    src="https://www.google.com/maps/embed?pb=!1m14!1m8!1m3!1d240.78824703625065!2d102.14699920619947!3d15.069564781872675!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x31194b032d576cc7%3A0x82d96dcfa95b07fc!2sHavana%20Korat!5e0!3m2!1sth!2sth!4v1660707077160!5m2!1sth!2sth"
                                    width="100%" height="100%" style="border:0;" allowfullscreen="" loading="lazy"
                                    referrerpolicy="no-referrer-when-downgrade"></iframe>
                            </div>
                        </div>
                    </div>

                    <!-- HUA Talay---------------------------------------------------------------- -->
                    <div class="tab-pane fade" id="pills-profile" role="tabpanel" aria-labelledby="pills-profile-tab">
                        <div class="row">

                            <div class="col-12 col-sm-12 col-md-12 col-lg-8 col-xl-8 col-xxl-8 p-2">
                                <div class="col-12">
                                    <div class="scrolling-wrapper row flex-row flex-nowrap pb-4">
                                        <div v-for="(items, index) in datacardH" :key="index" class="card p-0"
                                            @click="showdata(items)">
                                            <!-- <img class="cardimgpj"
                                                src="https://scontent.fbkk12-4.fna.fbcdn.net/v/t39.30808-6/293402896_567167925066341_2472675013874706989_n.jpg?_nc_cat=103&ccb=1-7&_nc_sid=730e14&_nc_eui2=AeH0Z8xY3vYv1YVbTXtbAi-xNgifeUUbm202CJ95RRubbWjN0d0m_V48ZKqHXGzZSeL8VKRx0Pd3mNjP_jVh0_1k&_nc_ohc=5ZaaoM8BYVYAX9W6N9P&_nc_ht=scontent.fbkk12-4.fna&oh=00_AT_MKpNPPeVUoC2-ZYCvpFoxi2e_3zvOw5IfRvGXqklfmw&oe=63071199"> -->
                                            <img class="logopj" v-bind:src="items.logo">
                                            <div class="card-body">
                                                <p class="nameproject">{{  items.project_Name  }}</p>
                                            </div>
                                        </div>
                                    </div>

                                </div>
                                <div class="col-12">
                                    <div class="carddetail mt-3">
                                        <div class="disble" v-show="showimgtitles">
                                            <div class="row">
                                                <div class="col-12 col-sm-12 col-md-12 col-lg-7 col-xl-7 col-xxl-7">
                                                    <img class="showimgdetail p-3"
                                                        src="https://images.unsplash.com/photo-1501183638710-841dd1904471?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80">
                                                </div>
                                                <div
                                                    class="col-12 col-sm-12 col-md-12 col-lg-4 col-xl-4 col-xxl-4 rowdetail">
                                                    <p class="title1 mt-4">projects</p>
                                                    <p class="title2">HUA<br>THALAE<br>ZONE.</p>
                                                    <p class="title3">Click on the card<br> above for details.</p>
                                                </div>
                                            </div>
                                        </div>

                                        <div class="row" v-show="showdetail">
                                            <div class="col-12 col-sm-12 col-md-12 col-lg-8 col-xl-8 col-xxl-8">
                                                <img class="showimgdetail p-3" v-for="(items, index) in imgcard"
                                                    :key="index" v-bind:src="items.pathfile"
                                                    v-show:src="index == imgindex">
                                            </div>
                                            <div
                                                class="col-12 col-sm-12 col-md-12 col-lg-4 col-xl-4 col-xxl-4 rowdetail">
                                                <p class="namecarddetail">{{  detailcard.project_Name  }}</p>
                                                <router-link :to="{ name: 'detail', params: { id: detailcard.id } }">
                                                    <p>Click for more details.</p>
                                                </router-link>
                                                <span class="locationdetail"><i class="fa-solid fa-house"></i>&nbsp;Type
                                                    of house :
                                                    &nbsp; {{  detailcard.detail  }}</span> <br>
                                                <span class="locationdetail"><i class="fa-solid fa-location-dot"></i>
                                                    &nbsp; {{  detailcard.zone  }}</span> <br>
                                                <span class="locationdetail"><i class="fa-solid fa-tags"></i>
                                                    &nbsp; START : {{  detailcard.price  }} M / THB</span>
                                                <p class="concepttitle">Concept :</p>
                                                <p class="content">{{  detailcard.concept  }} </p>
                                                <p>MORE IMAGE</p>
                                                <img class="imgmore" v-for="(items, index) in imgcard" :key="index"
                                                    v-bind:src="items.pathfile" @click="getindeximg(index)">
                                            </div>
                                        </div>


                                    </div>
                                </div>
                            </div>

                            <div class="col-12 col-sm-12 col-md-12 col-lg-4 col-xl-4 col-xxl-4 p-0">
                                <iframe class="map"
                                    src="https://www.google.com/maps/embed?pb=!1m14!1m8!1m3!1d240.78824703625065!2d102.14699920619947!3d15.069564781872675!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x31194b032d576cc7%3A0x82d96dcfa95b07fc!2sHavana%20Korat!5e0!3m2!1sth!2sth!4v1660707077160!5m2!1sth!2sth"
                                    width="100%" height="100%" style="border:0;" allowfullscreen="" loading="lazy"
                                    referrerpolicy="no-referrer-when-downgrade"></iframe>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

        </div>


    </div>
</template>
<script>
import axios from "axios";


export default {
    data() {
        return {
            datacardJ: [],
            datacardH: [],
            detailcard: [],
            imgcard: [],
            imgindex: 0,
            showimgtitles: true,
            showdetail: true
        }
    }, methods: {
        async showdata(value) {
            this.showimgtitles = false;
            this.showdetail = true;
            this.imgindex = 0;
            this.detailcard = value;
            // console.log(this.detailcard.id);
            await axios.get("https://www.u-sabai.com/api/web2/imagestorage.php?id=" + this.detailcard.id)
                .then((res) => (this.imgcard = res.data.filter(obj => {
                    return obj.imageProject === this.detailcard.id
                })));
            // for(var i=0;i<this.imgcard.length;i++){
            //     if(this.detailcard.id==this.imgcard[i].imageProject){
            //          console.log(this.imgcard[i].pathfile);
            //     }
            // }
        },
        getindeximg(value) {
            this.imgindex = value;
            console.log(this.imgindex);
        }


    },
    async mounted() {
        await axios.get("https://www.u-sabai.com/api/web2/projectdata.php")
            .then((res) => (this.datacardJ = res.data.filter(obj => {
                return obj.zone === "Choho"
            }), this.datacardH = res.data.filter(obj => {
                return obj.zone === "Huatalay"
            })));

        // console.log(res.data[0].zone)

        // await axios.get("https://www.u-sabai.com/api/web2/projectdata.php")
        //     .then((res) => (this.datacardH = res.data.filter(obj => {
        //         return obj.zone === "Huatalay"
        //     })));

        // ,this.datacard=res.data,console.log(this.datacard)
    }
}
</script>
<style scoped>
.container-fluid {
    background-color: #f7f7f7eb;
    height: 100vh;
    width: 100%;
    display: flex;
}


.scrolling-wrapper {
    overflow-x: auto;
    scrollbar-width: none;
}

.nav-link {
    background-color: rgb(255, 255, 255);
    color: #2b2d42;
    font-size: 26px;
}

.nav-link.active {
    background-color: #2b2d42;
}


.scrolling-wrapper {
    overflow-x: auto;
}

.card {
    background-color: rgb(255, 255, 255);
    max-width: 280px;
    border: none;
    box-shadow: 0px 0px 10px #ebebeb;
    border-radius: 10px;
    overflow: hidden;
    cursor: pointer;
    transition: 0.5s;
    margin-left: 10px;
}



.cardimgpj {
    width: 100%;
}

.nameproject {
    /* margin-top: 10px; */
    padding-top: 5px;
    font-size: 20px;
    font-weight: 500;
    margin-bottom: 0px;
}

.logopj {
    position: absolute;
    align-self: end;
    margin-top: 10px;
    margin-right: 10px;
    width: 50px;
}

.carddetail {
    background-color: rgb(255, 255, 255);
    max-width: 100%;
    height: 720px;
    box-shadow: 0px 0px 10px #ebebeb;
    border-radius: 10px;
    overflow: hidden;
}

.showimgdetail {
    width: 100%;
    height: 720px;
    border-radius: 10px;

    object-fit: cover;
    object-position: 50% 50%;
}

.namecarddetail {
    text-transform: uppercase;
    font-size: 26px;
    font-weight: 500;
    margin-bottom: 0;
}

.locationdetail {
    font-size: 14px;
    color: #747474;
}

.concepttitle {
    font-size: 14px;
    font-weight: 200;
    color: rgb(165, 165, 165);
    margin-top: 10px;
    margin-bottom: 0;
}

.content {

    font-size: 14px;
    font-weight: 300;
    word-wrap: break-word;
    width: 90%;
    text-align: justify;
    overflow: hidden;
    text-overflow: ellipsis;
    display: -webkit-box;
    -webkit-line-clamp: 4;
    line-clamp: 4;
    -webkit-box-orient: vertical;

}

.imgmore {
    width: 120px;
    height: 70px;
    margin-right: 10px;
    cursor: pointer;
    margin-top: 10px;
}


.map {
    border-radius: 10px;
    box-shadow: 0px 0px 10px #ebebeb;
}

.disble img {
    width: 100%;
}

.title1 {
    text-transform: uppercase;
    font-weight: 600;
    font-size: 36px;
}

.title2 {
    /* text-transform: uppercase; */
    text-transform: uppercase;
    font-weight: 600;
    font-size: 100px;
}

.title3 {
    text-transform: uppercase;
    /* font-size: 20px; */
}

.rowdetail {
    height: 580px;
}


@media only screen and (max-width: 820px) {

    .container-fluid {
        height: calc(100vh - calc(100vh - 100%));
    }

    .nav-link {
        font-size: 16px;
    }

    .card {
        max-width: 200px;
    }

    .logopj {
        width: 35px;
    }

    .nameproject {

        font-size: 16px;

    }

    .carddetail {

        width: 100%;
        height: 800px;

    }

    .showimgdetail {
        width: 100%;
        height: 400px;
        border-radius: 10px;

        object-fit: cover;
        object-position: 50% 50%;
    }


    .title1 {
        font-size: 26px;
    }

    .title2 {

        font-size: 70px;
    }

    .title3 {

        font-size: 16px;
    }

    .namecarddetail {
        font-size: 18px;
    }

    .content {


        word-wrap: break-word;
        width: 90%;
        text-align: justify;
        overflow: hidden;
        text-overflow: ellipsis;
        display: -webkit-box;
        -webkit-line-clamp: 2;
        line-clamp: 2;
        -webkit-box-orient: vertical;

    } 

    .imgmore {
    width: 100px;
    height: 60px;
    margin-right: 10px;
    cursor: pointer;
    margin-top: 10px;
}

.rowdetail {
    height: 480px;
    width: 100%;
    margin-left: 3%;
    /* padding: ; */
}

}

@media only screen and (max-width: 600px) {
    .container-fluid {
        height: calc(100vh - calc(100vh - 100%));
    }

    .nav-link {
        font-size: 16px;
    }

    .card {
        max-width: 200px;
    }

    .logopj {
        width: 35px;
    }

    .nameproject {

        font-size: 16px;

    }

    .carddetail {

        width: 100%;
        height: 800px;

    }

    .showimgdetail {
        width: 100%;
        height: 250px;
        border-radius: 10px;

        object-fit: cover;
        object-position: 50% 50%;
    }


    .title1 {
        font-size: 26px;
    }

    .title2 {

        font-size: 70px;
    }

    .title3 {

        font-size: 16px;
    }

    .namecarddetail {
        font-size: 18px;
    }

    .content {


        word-wrap: break-word;
        width: 90%;
        text-align: justify;
        overflow: hidden;
        text-overflow: ellipsis;
        display: -webkit-box;
        -webkit-line-clamp: 2;
        line-clamp: 2;
        -webkit-box-orient: vertical;

    }

}
</style>