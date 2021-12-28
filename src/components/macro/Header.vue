<template>
  <header>
      <img src="../../assets/img/netflix.png" alt="">
      <nav>
        <ul>
            <li>Home</li>
            <li>Serie TV</li>
            <li>Film</li>
            <li>Nuovi e Popolari</li>
            <li>La mia lista</li>
        </ul>
      </nav>
  </header>
</template>

<script>
export default {
    name: "Header"
}
</script>

<style lang="scss" scoped>
    header{
        height: 70px;
        width: 100%;
        background-color: #141414;
        display: flex;
        align-items: center;
        justify-content: space-between;
        padding: 0 50px;
        position: fixed;
        z-index: 1;
    };

    img{
        height: 70px;
    };

    nav{
        ul{
            display: flex;
            color: white;
            list-style: none;

            li{
                padding: 10px;
            }
        }
    }
</style>