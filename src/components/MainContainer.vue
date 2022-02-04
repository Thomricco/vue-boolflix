<template>
    <main>
        <div class="container-box-img">
            <film-box v-for="film in films"
            :key=film.id
            :film="film" />

            <serie-box v-for="serie in series"
            :key=serie.id
            :serie="serie" />
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
    .container-box-img {
        width: 1200px;
        display: flex;
        flex-wrap: wrap;
    }
</style>