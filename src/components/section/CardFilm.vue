<template>
  <section>
      <div class="anteprima">
        <img v-if="info.backdrop_path" :src="`https://image.tmdb.org/t/p/w342/${info.backdrop_path}`" alt="img">
        <img v-else src="../../assets/img/riciak.jpg" alt="img" width="342px">
      </div>

      <div class="info">
        <p>{{info.title || info.name}}</p>
        <p>{{info.original_title || info.original_name}}</p>
        <img v-if="flags.includes(info.original_language)" :src="require(`../../assets/img/${info.original_language}.png`)" :alt="info.original_language">
        <img v-else src="../../assets/img/eu.png" alt="img">
        <div class="star" v-show="stelle == 0">
          <i class="far fa-star"></i>
          <i class="far fa-star"></i>
          <i class="far fa-star"></i>
          <i class="far fa-star"></i>
          <i class="far fa-star"></i>
        </div>
        <div class="star" v-show="stelle == 1">
          <i class="fas fa-star"></i>
          <i class="far fa-star"></i>
          <i class="far fa-star"></i>
          <i class="far fa-star"></i>
          <i class="far fa-star"></i>
        </div>
        <div class="star" v-show="stelle == 2">
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="far fa-star"></i>
          <i class="far fa-star"></i>
          <i class="far fa-star"></i>
        </div>
        <div class="star" v-show="stelle == 3">
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="far fa-star"></i>
          <i class="far fa-star"></i>
        </div>
        <div class="star" v-show="stelle == 4">
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="far fa-star"></i>
        </div>
        <div class="star" v-show="stelle == 5">
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
        </div>
      </div>
      
      
  </section>
</template>

<script>
export default {
    name: "CardFilm",
    props:{
        info: Object
    },
    data(){
        return{
            flags: [
                "it",
                "fr",
                "ja",
                "en",
                "es"
            ],
        }
    },
    computed: {
        stelle(){
          return Math.ceil(this.info.vote_average / 2);
        }
    },
}
</script>

<style lang="scss" scoped>
  section{
    position: relative;
    margin: 5px;
    cursor: pointer;
    
  }

    .anteprima{
      img{
        width: 290px;
        height: 180px;
      };
    };
    section:hover .anteprima{
      opacity: 0.3;
    };

    section:hover .info{
      visibility: visible;
    }

    .info{
      position: absolute;
      top: 0;
      left: 0;
      visibility: hidden;
    };

    .star{
      color: rgba(216, 216, 6, 0.781);
    }

</style>