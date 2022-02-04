<template>
    <main>
        <div class="container-box-img">
            <film-box v-for="film in films"
            :key=film.id
            :film="film" />
        </div>
    </main>
</template>

<script>

import FilmBox from './FilmBox.vue'

export default {
    components: {
        FilmBox,
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