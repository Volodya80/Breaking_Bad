<template>
 <div id="app">
  <header>
    <div class="header-title">rrew</div>
  </header>
  <nav>
    <MyMenu />
  </nav>
  <main>
    <Nuxt />
  </main>
  <footer>
    <h3>I'm a little area</h3>
  </footer>
</div>
</template>

<script>
import MyMenu from "@/components/menu"
export default {
  components: {
    MyMenu
  }
}

</script>

<style lang="scss">
$txt-color: #a3eb87;
$txt-color-hover: #FFFFFF;
$bk-color: #313f2d; 

      #app {
          display: grid;
          
          grid-template-columns: 1fr 3fr;
          grid-template-rows: 15vh 80vh 5vh;
          grid-template-areas: "a a"
                              "b c"
                              "d d";
          /* align-content: initial; */
          align-content: space-around;
          
        header {
          grid-area: a;
          border: 1px solid transparent;

          background-image: url('@/assets/img/header_img_0.png');
          background-position: top right;
          background-repeat: no-repeat;
          background-size: contain;

          background-color: #000000;

          color: white;
          /* background-origin:content-box; */
      
            header-title {
              position: relative;

              width: 20vw;
              height: 90%;

              top: 0;
              left: 0;

              background-image: url('@/assets/img/Breaking_Bad_logo.svg');
              background-repeat: no-repeat;
              background-position: top left;
              background-size: contain;

              border: 1px solid yellow;
            } //header-title
        } // header
        nav {
          grid-area: b;

          background-color: $bk-color;
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
