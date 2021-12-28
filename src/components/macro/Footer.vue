<template>
  <footer>
      <div class="container">
          <section class="img">
          <i class="fab fa-facebook-f"></i>
          <i class="fab fa-instagram"></i>
          <i class="fab fa-twitter"></i>
          <i class="fab fa-youtube"></i>
      </section>

      <section class="links">
          <div>
              <ul>
                  <li>Audio e sottotitoli</li>
                  <li>Media Center</li>
                  <li>Privacy</li>
                  <li>Contattaci</li>
              </ul>
          </div>
          <div>
              <ul>
                  <li>Audiodescrizione</li>
                  <li>Rapporti con gli investitori</li>
                  <li>Note legali</li>
              </ul>
          </div>
          <div>
              <ul>
                  <li>Centro assistenza</li>
                  <li>Opportunità di lavoro</li>
                  <li>Preferenze per i cookie</li>
              </ul>
          </div>
          <div>
              <ul>
                  <li>Carte regalo</li>
                  <li>Condizioni di utilizzo</li>
                  <li>Informazioni sull'azienda</li>
              </ul>
          </div>
      </section>

      <section class="codice">
          <div class="servizio">
              <span>Codice di servizio</span>
          </div>
          <div>
              <p>1997-2001 Netflix, Inc. {c9wr23r92r923er92304e92304}</p>
          </div>
      </section>
      </div>
      
  </footer>
</template>

<script>
export default {
    name: "Footer"
}
</script>

<style lang="scss" scoped>

    footer{
        height: 400px;
        background-color: #141414;

        .container{
        width: 60%;
        padding-top: 50px;
        };

        .img{
            color: white;
            padding-left: 50px;

            i{
                width: 50px
            }
        };

        .links{
            display: flex;
            justify-content: space-between;
            color: grey;

            ul{
                list-style: none;

                li{
                    padding: 10px;
                }
            }
        };

        .codice{
            padding-left: 40px;
            color: grey;

            .servizio{
                margin-bottom: 20px;
            }

            span{
                border: 1px solid grey;
                padding: 5px 10px;
            }
        }
    }
        

</style>