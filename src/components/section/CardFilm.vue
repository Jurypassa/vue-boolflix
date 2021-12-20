<template>
  <div>
      <p>{{info.title}}</p>
      <p>{{info.original_title}}</p>
      <p>{{info.original_language}}</p>
      <p>{{info.vote_average}}</p>
  </div>
</template>

<script>
export default {
    name: "CardFilm",
    props:{
        info: Object
    }
}
</script>

<style lang="scss" scoped>

</style>