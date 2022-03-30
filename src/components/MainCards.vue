<template>
    <div class="card text-center p-3" >
        <img :src="songPoster" class="card-img-top" :alt="songTitle">
        <div class="card-body">
            <h4 class="card-title text-white">{{songTitle}}</h4>
            <span class="card-text">{{songAuthor}}</span>
            <span class="card-text d-block">{{songYear}}</span>
        </div>
    </div>
</template>

<script>


export default {
    name: "MainCardsIndex",
    props:['songPoster', 'songTitle', 'songAuthor', 'songYear']
}
</script>

<style lang="scss" scoped>
    .card{
        background-color: #2e3a46;
        width: calc(80% / 5);
        margin: 10px 2%;
        height: 350px;
        span{
            color: #807f80;
        }
    }
</style>