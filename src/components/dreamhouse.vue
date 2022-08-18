<template>
    <div class="container-fluid">
        <div class="row">
            <div class="col-6">
               <div class="container p-4">
                <img class="imghouse" src="https://images.unsplash.com/photo-1660610998438-ec7f7da65406?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80"/>
               </div>
            </div>
            <div class="col-6 p-0 content">
               <div class="container p-5">
                <p class="mt-5">Find your<br>dream<br>house</p>
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
    .imghouse{
        width:100%;
        box-shadow: inset 0px 0px 10px rgba(0, 0, 0, 0.327);
    }
    .content{
        background-color: #272727;
    }
    .content p{
        color :aliceblue;
        text-transform: uppercase;
        font-size: 100px;
        font-weight: 500;
        margin:0 ;
    }
</style>