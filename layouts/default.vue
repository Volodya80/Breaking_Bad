<template>
 <div id="app">
  <header>
    <MyHeader />
  </header>
  <nav>
    <MyMenu />
  </nav>
  <main>
    <Nuxt />
  </main>
  <footer>
    <MyFooter />
  </footer>
</div>
</template>

<script>
import MyMenu from "@/components/menu"
import MyFooter from "@/components/my-footer"
import MyHeader from "@/components/myheader"
export default {
  components: {
    MyMenu,
    MyHeader,
    MyFooter
  }
}

</script>

<style lang="scss">
$txt-color: #a3eb87;
$txt-color-hover: #FFFFFF;
$bk-color: #313f2d;

      #app {
          display: grid;
          @media screen and (min-width:1000px) {
            grid-template-columns: 1fr 3fr;
            grid-template-rows: 15vh minmax(80vh, auto) 5vh;
            grid-template-areas: "a a"
                                "b c"
                                "d d";
            /* align-content: initial; */
          }
          @media (min-width: 400px) and (max-width: 1000px) {
            grid-template-columns: 1fr;
            //grid-template-rows: repeat(4, 100px);
            grid-template-areas: "a"
                                "b"
                                "c"
                                "d";
          }
          align-content: space-around;
          
        header {
          grid-area: a;
        } // header
        nav {
          grid-area: b;

          //background-color: $bk-color;
          border: 1px solid blue;
        }
        main {
          grid-area: c;
          border: 1px solid green;
        }
        footer {
          grid-area: d;
          border: 1px solid red;
        }
      }


</style>
