<template>
    <div class="container-fluid mt-5">
        <div class="container">
            <p class="title">can your choore</p>
        </div>
        <div class="row">
            <div class="col">
                <cardpj />
            </div>
        </div>


    </div>
</template>
<script>
import cardpj from '@/widgets/cardpj.vue'
export default {
    components: {
        cardpj
    }
}
</script>

<style scoped>
.title {
    text-transform: uppercase;
    font-size: 36px;
}
</style>