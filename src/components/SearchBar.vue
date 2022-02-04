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

export default {
    data() {
        return {
            keywordSearch: ''
        }
    }
    
}
    

</script>

<style lang="scss" scoped>

</style>