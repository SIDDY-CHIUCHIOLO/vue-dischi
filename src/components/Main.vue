<template>
    <main class="d-flex flex-wrap justify-content-center align-items-center">
        <div class="container bg-danger">
            <div class="row">
                <div class="col-12">
                    <MainCards/>
                </div>
            </div>
        </div>
    </main>
</template>

<script>
import MainCards from './MainCards.vue'

export default {
    name: "MainIndex",
    components:{
        MainCards,
    }
}
</script>

<style lang="scss">
    main{
        background-color: #1e2d3b;
        height: 90vh;
    }
</style>