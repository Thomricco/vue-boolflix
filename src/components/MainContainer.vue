<template>
    <main>
        <div class="container">
            <div class="ins">
                
                <h2>FILM DEL MOMENTO</h2>
            </div>
            <div class="container-box-img">
                
                <film-box v-for="film in films"
                :key=film.id
                :film="film" />

            </div>

            <div class="ins">
                
                <h2>SERIE TV DEL MOMENTO</h2>
            </div>

            <div class="container-box-img">
                <serie-box v-for="serie in series"
                :key=serie.id
                :serie="serie" />
            </div>
        </div>

        
    </main>
</template>

<script>

import FilmBox from './FilmBox.vue'
import SerieBox from './SerieBox.vue'

export default {
    components: {
        FilmBox,
        SerieBox
    },
    props: {
        films: Array,
        series: Array
    }
    
}
</script>

<style lang="scss" scoped>

main {
    margin: 0 auto;
    background-color: black;
    .container {
        .ins {
            
            color: #fff;
            padding: 30px;
        }
        .container-box-img {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            padding: 10px;
            
        }       
    }

}

</style>