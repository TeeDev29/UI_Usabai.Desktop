<template >
    <div class="container-fluid ">

        <div class="row">

            <div class="col-6 p-5 text-end">
                <!-- <div class="circle"></div>
                <div class="circle2"></div>
                <div class="circle3"></div> -->
                <p class="title mt-3">If you're <br> interested,</p>
                <p class="content"> come take a look <br>at our model homes first.</p>
                <p style="color: aliceblue;">LOCATION</p>
                <div class="mb-4">
                    <button type="button" class="btn btn-light" @click="tigglemap(true)">JOHO</button> &nbsp;
                    <button type="button" class="btn btn-light" @click="tigglemap(false)">HUA TALAY</button>
                </div>
            </div>
            <div class="col-6 p-4 map">
                <iframe v-show="showmapj"
                    src="https://www.google.com/maps/embed?pb=!1m14!1m8!1m3!1d240.78824703625065!2d102.14699920619947!3d15.069564781872675!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x31194b032d576cc7%3A0x82d96dcfa95b07fc!2sHavana%20Korat!5e0!3m2!1sth!2sth!4v1660707077160!5m2!1sth!2sth"
                    width="100%" height="100%" style="border:0;" allowfullscreen="" loading="lazy"
                    referrerpolicy="no-referrer-when-downgrade"></iframe>
                <iframe v-show="showmaph"
                    src="https://www.google.com/maps/embed?pb=!1m14!1m8!1m3!1d3854.7892209843953!2d102.16718!3d14.948832!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x0%3A0xe12daaed083539d4!2z4Lia4LmJ4Liy4LiZ4Lit4Lii4Li54LmI4Liq4Lia4Liy4LiiIOC5guC4i-C4meC4q-C4seC4p-C4l-C4sOC5gOC4pQ!5e0!3m2!1sth!2sth!4v1660804456232!5m2!1sth!2sth"
                    width="100%" height="100%" style="border:0;" allowfullscreen="" loading="lazy"
                    referrerpolicy="no-referrer-when-downgrade"></iframe>
            <!-- <p>{{showmap}}</p> -->
            </div>
        </div>
    </div>
</template>
<script>
export default {
    data() {
        return {
            showmap :false,
            showmapj: false,
            showmaph: true,
        }
    }
    , methods: {
        tigglemap(value) {
           this.showmapj = value;
           this.showmaph = !value;
        }
    }
}
</script>
<style scoped>
.container-fluid {
    background-color: #272727;
}

.title {
    color: #272727;
    text-transform: uppercase;
    font-size: 72px;
    font-weight: bold;
    -webkit-text-stroke: 3px rgb(255, 255, 255);
}

.content {
    color: #ffffff;
    text-transform: uppercase;
    font-size: 36px;
    font-weight: 500;

}

iframe {
    /* border-radius: 10px; */
}

.map {
    background-color: #ffffff;
}

/* .circle {
    
    position: absolute;
    min-width: 300px;
    min-height: 300px;
    background: linear-gradient(90deg, rgba(255, 15, 123, 0.829) 0%, hsla(33, 94%, 57%, 1) 100%);
    border-radius: 50%;
     opacity: 80%;
}

.circle2 {
    margin-left: 12%;
    margin-top: 12%;
    position: absolute;
    min-width: 200px;
    min-height: 200px;
    background: linear-gradient(90deg, hsla(270, 94%, 25%, 1) 0%, hsla(158, 94%, 49%, 1) 100%);
    border-radius: 50%;
    opacity: 30%;
}

.circle3 {
    margin-left: 4%;
    margin-top: 16%;
    position: absolute;
    min-width: 150px;
    min-height: 150px;
    background: linear-gradient(90deg, hsla(141, 54%, 86%, 1) 0%, hsla(333, 73%, 85%, 1) 50%, hsla(211, 58%, 79%, 1) 100%);
    border-radius: 50%;
    opacity: 50%;
} */
</style>