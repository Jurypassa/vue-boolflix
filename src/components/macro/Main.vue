<template>
  <div>
      <input v-model="Search" type="text" placeholder="Inserisci il titolo">
      <button @click="ListaFilm">Cerca</button>
      <div v-for="(card, index) in TitoliFiltrati" :key="index">
        <CardFilm :info="card"/>
      </div>
  </div>
</template>

<script>
import CardFilm from "../section/CardFilm.vue";
import axios from "axios";

export default {
  name: "Main",
  components:{
    CardFilm,
  },
  data(){
    return{
      Titoli: [],
      Search: ""
    }
  },
  methods: {
    ListaFilm(){
      axios.get('https://api.themoviedb.org/3/search/movie', {
        params: {
          api_key: "073691ba15bec70d857f6e60347f02c7",
          query: this.Search
        }
      })
      .then((response) => {
        this.Titoli = response.data.results;
      })
      .catch(function (error) {
        console.log(error);
      })
    },
    RicercaTitoli(payload){
      this.Search = payload;
    },
  },
  computed: {
    TitoliFiltrati(){
      return this.Titoli.filter((elm) => {
          return elm.title.includes(this.Search);
      })
    }
  }
}  
</script>

<style lang="scss" scoped>


</style>