<template>
    <header>
        <nav>
            <div>
                <input type="text" placeholder="Search"
                v-model="keywordSearch"
                @keyup.enter="$emit('search', keywordSearch)" />
            </div>
        </nav>
    </header>
</template>

<script>
import axios from 'axios'
export default {
    data() {
        return {
            keywordSearch: ''
        }
    },
    methods: {
        resetAll() {
            this.keywordSearch = axios.get ('https://api.themoviedb.org/3/search/movie?&api_key=e99307154c6dfb0b4750f6603256716d&query= + "keywordSearch"')
        }
    }
}
    

</script>

<style lang="scss" scoped>

</style>