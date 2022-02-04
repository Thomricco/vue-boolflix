<template>
    <header>
        <nav>
            <img src="https://image.tmdb.org/t/p/w342/wwemzKWzjKYJFfCeiB57q3r4Bcm.png" alt="">
            <div class="componenti">
                
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

header {
    background-color: black;
    height: 50PX;
    margin: 0 auto;
    nav {
        display: flex;
        justify-content: space-between;
        padding-left: 10px;
        padding-right: 10px;

        img {
            height: 50px;
        }
        .componenti {
            display: flex;
            align-items: center;

            input {
                height: 30px;
            }
        }

    }
}

</style>