<template>
    <div class="film">
        <div class="front">
            <img :src="`https://www.themoviedb.org/t/p/original${film.poster_path}`" alt="">
            <div class="back">
                <p>{{film.title}}</p>
                <p>{{film.original_title}}</p>
                <p>{{film.original_language}}</p>
                <p>{{film.vote_average}}</p>
            </div>
        </div>
        
    </div>
</template>

<script>
export default {
    props: {
        film: Object
    }
}
</script>

<style lang="scss" scoped>
.film {
    width: 200px;
    height: 350px;
    text-align: center;
    border: 1px gray solid;
    margin: 10px;

    .front {
        cursor: pointer;
        width: 200px;
        height: 350px;
        :hover{
            display: none;
        } 
        img {
            width: 200px;
            height: 350px;
            background-size: contain;
            :hover{
              display: none;
            }
        }

    }
   
    
    .back {
        width: 200px;
        height: 350px;
        cursor: pointer;
        border: 2px red solid;
        display: none;
       
        :hover {
            display: inline-block;
        }
    }
    

   
}
</style>