<template>
    <div class="movie-detail">
        <h2>{{movie.Title}}</h2>
        <p>{{ movie.Year }}</p>
        <img :src="movie.Poster" alt="" class="featured-image"/>
        <p>{{ movie.Plot }}</p>
    </div>
</template>   

<script>

import { ref, onBeforeMount } from 'vue';
import { useRoute} from 'vue-router';
import env from '@/env.js'

export default {
    setup () {
        const movie = ref ({});
        const route = useRoute();

        onBeforeMount(() => {
            fetch(`https://www.omdbapi.com/?apikey=${env.apikey}&i=${route.params.id}&plot=full`)
            .then(res => res.json())
            .then(data => {
                movie.value = data;
            })
        })
        return {
            movie
        }
    }
}

</script>

<style lang="scss">
    .movie-detail {
        padding: 16px;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        background-color: #27496D;

        h2 {
            color: #FFF;
            font-size: 28px;
            font-weight: 600;
            margin-bottom: 16px;
        }
        
        .featured-image {
            display: block;
            max-width: 240px;
            margin-bottom: 16px;
        }

        p {
            color: #FFF;
            font-size: 18px;
            line-height: 1.4;
            margin-bottom: 10px;
            max-width: 270px;
        }
    }   
</style>