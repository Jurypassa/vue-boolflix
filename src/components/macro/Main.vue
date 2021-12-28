<template>
  <main>
    <div class="ricerca">
      <input v-model="Search" type="text" placeholder="Inserisci il titolo">
      <button @click="ListaFilm">Cerca</button>
    </div>
      <h2>Lista Film:</h2>
      <div class="clearfix">
        <div class="float" v-for="(card, index) in TitoliFilm" :key="index">
        <CardFilm :info="card"/>
      </div>
      </div>
      
      <h2>Lista Serie TV:</h2>
      <div class="clearfix">
        <div class="float" v-for="(card, index) in TitoliSerie" :key="index">
        <CardFilm :info="card"/>
      </div>
      </div>
      
  </main>
</template>

<script>
import '@fortawesome/fontawesome-free/css/all.css'
import '@fortawesome/fontawesome-free/js/all.js'
import CardFilm from "../section/CardFilm.vue";
import axios from "axios";

export default {
  name: "Main",
  components:{
    CardFilm,
  },
  data(){
    return{
      TitoliFilm: [],
      TitoliSerie: [],
      Search: "",
      oldSearch: ""
    }
  },
  methods: {
    ListaFilm(){
      if( this.Search != this.oldSearch ) {
        axios.get('https://api.themoviedb.org/3/search/movie/', {
          params: {
            api_key: "073691ba15bec70d857f6e60347f02c7",
            query: this.Search
          }
        })
        .then((response) => {
          this.TitoliFilm = response.data.results;
          this.oldSearch = this.Search;
        })
        .catch(function (error) {
          console.log(error);
        }),

        axios.get('https://api.themoviedb.org/3/search/tv/', {
          params: {
            api_key: "073691ba15bec70d857f6e60347f02c7",
            query: this.Search
          }
        })
        .then((response) => {
          this.TitoliSerie = response.data.results;
          this.oldSearch = this.Search;
        })
        .catch(function (error) {
          console.log(error);
        })
      }
    },
    RicercaTitoli(payload){
      this.Search = payload;
    },
  },
  
}  
</script>

<style lang="scss" scoped>
  main{
    padding: 70px 50px 0 50px;
    width: 100%;
    min-height: calc(100vh - 400px);
    color: white;
  };

  h2{
    padding: 30px 0;
  }

  .clearfix:after{
    content: "";
    display: table;
    clear: both;
  };

  .float{
    // display: flex;
    float: left;
  }

  .ricerca{
    text-align: center;
    padding: 30px;

    input{
      width: 500px;
      height: 40px;
      border: 2px solid lightgray;
      border-radius: 10px;
      color: grey;
    };

    button{
      margin-left: 30px;
      border: 2px solid lightgrey;
      border-radius: 10px;
      padding: 5px 10px;
    }
  }

</style>