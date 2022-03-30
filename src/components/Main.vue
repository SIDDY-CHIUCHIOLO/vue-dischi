<template>
    <main class="d-flex flex-wrap justify-content-center align-items-center">
        <div v-if="listSpotifySongs"  class="container">
            <div class="row">
                <div class="col-12">
                    <div id="my-container-cards" class="d-flex flex-wrap justify-content-center align-items-center p-5">
                        <MainCards
                            v-for="(element, index) in listSpotifySongs"
                            :key="index"
                            :songPoster="element.poster"
                            :songTitle="element.title"
                            :songAuthor="element.author"
                            :songYear="element.year"
                        />
                    </div>
                </div>
            </div>
        </div>
        <div v-else class="container-fluid my-container-load">
            <div class="row text-center">
                <div class="col-12">
                    <div class="contain-load">
                        <p class="fw-bold text-white fs-6">LOADING</p>
                    </div>
                </div>
            </div>
        </div>
    </main>
</template>

<script>
import axios from 'axios';

import MainCards from './MainCards.vue'

export default {
    name: "MainIndex",
    data: function(){
        return{
            listSpotifySongs: null,
        }
    },
    components:{
        MainCards,
    },
    created: function(){
        setTimeout(this.apiSpotifySongs, 5000, this.listSpotifySongs)
    },
    methods:{
        apiSpotifySongs(){
            axios
            .get('https://flynn.boolean.careers/exercises/api/array/music')
            .then((result) =>{
                this.listSpotifySongs = result.data.response
                console.log(this.listSpotifySongs)
            })
            .catch((error)=>{
                console.log(error);
            })
        }
    }
}
</script>

<style lang="scss">
    main{
        background-color: #1e2d3b;
        .my-container-load{
            height: 90vh;
            background-image: url("../assets/load.gif");
            background-repeat: no-repeat;
            background-size: cover;
            background-position: center;
            overflow: hidden;
            background-color: #262626;
            .contain-load{
                line-height: 90vh;
            }
        }
    }
</style>