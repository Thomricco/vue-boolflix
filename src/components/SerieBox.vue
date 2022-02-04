<template>
    <header>
        <div class="film-img">
           
            <div class="film-descrizione">
                <img :src="`https://www.themoviedb.org/t/p/original${serie.poster_path}`" alt="">
                <p>{{serie.name}}</p>
                <p>{{serie.original_name}}</p>
                <p>{{serie.original_language}}</p>
                <p>{{serie.vote_average}}</p>
            </div>
        </div>
        
    </header>
    

    
    
</template>

<script>
export default {
    props: {
        serie: Object
    }
}
</script>

<style lang="scss" scoped>
header {
    margin: 0 auto;

    .film-img {
    width: 200px;
    height: 350px;
    border: 1px gray solid;
    margin: 10px;


    .film-descrizione {
        cursor: pointer;
        width: 200px;
        height: 350px;
        background-color: black;
        color: black;
        font-size: 15px;
        

        &:hover {
            cursor: pointer;
            width: 200px;
            height: 350px;
            background-color: black;
            color: #fff;
            font-size: 15px;
        }
        img {
        width: 200px;
        height: 350px;
        background-size: contain;
        cursor: pointer;
        
        &:hover {
            display: none;
        }
        
    }

}
}


    
}
</style>