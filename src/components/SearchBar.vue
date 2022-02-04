<template>
    <header>
        <nav>
            <div>
                <input type="text" placeholder="Search"
                v-model="movieSearch"
                @keyup.enter="$emit('search', movieSearch)" />
            </div>
        </nav>
    </header>
</template>

<script>

export default {
    data() {
        return {
            movieSearch: '',
        }
    }
    
}
    

</script>

<style lang="scss" scoped>

</style>