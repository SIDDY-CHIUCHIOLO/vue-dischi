<template>
    <div class="col-2">
        <div class="card text-center" >
            <img src="@/assets/logo-spotify.png" class="card-img-top" alt="...">
            <div class="card-body">
                <h1 class="card-title text-white">Card title</h1>
                <span class="card-text">boom</span>
                <span class="card-text d-block">boom</span>
            </div>
        </div>
    </div>
</template>

<script>


export default {
    name: "MainCardsIndex",
}
</script>

<style lang="scss" scoped>
    .card{
        background-color: #2e3a46;
        span{
            color: #807f80;
        }
    }
</style>