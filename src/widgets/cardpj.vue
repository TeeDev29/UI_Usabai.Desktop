<template>
    <div class="card m-3">
        <div class="row">
            <div class="col-7">
                <img class="imghome pt-5 ps-5 pb-5 pe-0" src="https://scontent.fbkk9-2.fna.fbcdn.net/v/t39.30808-6/299779841_589904789459321_8351117746682359241_n.jpg?_nc_cat=109&ccb=1-7&_nc_sid=730e14&_nc_eui2=AeHQ3jm4KZKhYVJfjNLg2fFs8Nf2DT8wYCnw1_YNPzBgKS6QgPsSwA1qi2T5nd0iEiURRxmTf5D0N0NHCNU91pfw&_nc_ohc=olykWhC2AWQAX-nYwGt&_nc_ht=scontent.fbkk9-2.fna&oh=00_AT92Yh_Sr4K_rJwbVx4yZQ3tqw9HuYcsiZHWZyI6v1BlJQ&oe=6300D00E"/>
            </div>
            <div class="col-5 d-flex">
                <div class="row ps-0 pt-5 pb-5 pe-5">
                    <div class="col-12">
                       <span> <img class="logo" src="@/assets/ESTELLA.png" /><span class="nameproject ms-2">the vela</span></span>
                    </div>
                    <div class="col-12">
                        <p>Detail</p>
                        <span class="typetitle">Type of house :</span><span class="hastax">&nbsp;#single storey house &nbsp;#two-story detached house</span>
                        <p class="concepttitle">Concept :</p>
                        <p class="content">It is the last project of Baan Yu Sabai, Hua Talay Zone. There are four roads cut through. Near Somdej Phra Thep Garden * The project is quiet, suitable for living. Surrounded by nature * Design a home to be perfect. </p>
                   </div>
                   <div class="col-12 bottomcontent">
                    <span class="loandpititle">Location :</span> <span>Hua Talay</span> &nbsp;
                    <span class="loandpititle">Starting price :</span> <span>2,000,000 THB</span>
                   </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    
}
</script>
<style scoped>
    .card{
        border: none;
       /* min-height: 610px; */
        max-width: 1300px;
        /* box-shadow: 0px 0px 15px #e3e3e3;
        border-radius: 10px; */
       
    }
    .imghome{
        width: 100%;
    }
    .logo{
       max-width: 100px;
       max-height: 100px;
        /* background-color: aqua; */
    }
    .nameproject{
        text-transform: uppercase;
        font-size: 36px;

    }
    .typetitle{
        font-size: 16px;
        font-weight: 200;
        color:rgb(165, 165, 165)
    }
    .hastax{
        font-weight: 400;
    }
    .concepttitle{
         font-size: 16px;
        font-weight: 200;
        color:rgb(165, 165, 165);
        margin-top: 10px;
        margin-bottom: 0;
    }
.content{
    font-size: 16px;
    font-weight: 300;
    text-align: justify;
}
.loandpititle{
        font-size: 14px;
        font-weight: 200;
        color:rgb(165, 165, 165);
        margin-top: 10px;
        margin-bottom: 0;
}
.bottomcontent{
  align-self: flex-end;
}
</style>