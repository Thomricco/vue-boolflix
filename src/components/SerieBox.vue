<template>
    <header>
        <div class="serie-img">
           
            <div class="serie-descrizione">
                <div class="immagine">
                    <img :src="`https://www.themoviedb.org/t/p/original${serie.poster_path}`" alt="">
                </div>

                <div class="testo">
                    <p>{{ serie.name }}</p>
                    <p>{{ serie.original_name }}</p>
                    <p v-if="serie.original_language == 'en'"><img src="https://flagcdn.com/16x12/gb-eng.png" srcset="https://flagcdn.com/32x24/gb-eng.png 2x,https://flagcdn.com/48x36/gb-eng.png 3x " width="16" height="12" alt="England"/></p>
                    <p v-if="serie.original_language == 'it'"><img src="https://flagcdn.com/16x12/it.png" srcset="https://flagcdn.com/32x24/it.png 2x, https://flagcdn.com/48x36/it.png 3x " width="16" height="12" alt="Italy"/></p>
                    <p v-if="serie.original_language == 'es'"><img src="https://flagcdn.com/16x12/es.png" srcset="https://flagcdn.com/32x24/es.png 2x,https://flagcdn.com/48x36/es.png 3x" width="16" height="12" alt="Spain"/></p>
                    <p v-if="serie.original_language == 'fr'"><img src="https://flagcdn.com/16x12/fr.png" srcset="https://flagcdn.com/32x24/fr.png 2x,https://flagcdn.com/48x36/fr.png 3x" width="16" height="12" alt="France"/></p>
                    <p v-else>{{ serie.original_language }}</p>
                    <p>{{ Math.round(serie.vote_average) }}"</p>
                </div>
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
  .serie-img {
    width: 200px;
    height: 350px;
    // border: 1px gray solid;
    margin: 10px;

    .serie-descrizione {
      width: 200px;
      height: 350px;
      position: relative;
      &:hover {
         .immagine  {
          display: none;
        }
      }
      .immagine {
        position: absolute;
        top: 0;
        left: 0;
        img {
          width: 200px;
          height: 350px;
          cursor: pointer;
        }
      }
      .testo {
        width: 200px;
        height: 350px;
        color: #fff;
      }
    }
  }
}
</style>