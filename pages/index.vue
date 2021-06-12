<template>
  <div class="mycontainer">
    <div class="inner">
      <p class="text-primary h2 my-3">Во все тяжкие</p>
      <p class="text-white">Американский телевизионный сериал, в котором показана история школьного учителя <strong>Уолтера Уайта</strong>,
      у которого дианостировали неоперабельный рак лёгких. Вместе со своим бывшим учеником <strong>Джесси Пинкманом</strong> 
      он начинает производить и продавать метамфетамин, чтобы обеспечить финансовое будущее своей семьи.
      </p>
      <iframe width="400" height="200" src="https://www.youtube.com/embed/L5l3vv9n7EU" 
        title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; 
        clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen>
      </iframe>
    </div>
  </div>
    
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.mycontainer {
  
  width: 100%;
  height: 100%;

  top: 0;
  left: 0;


  position: relative;
  
  background-image: url('@/assets/img/index_img.jpg');
  
  background-size: cover;
  background-repeat: no-repeat;


  .inner {
    
    position: relative;
    border: 1px solid transparent;

    @media screen and (min-width:1000px) {
        width: 30vw;
    }

    padding-top: 2%;
    padding-left: 3%;

    >iframe {
      @media (max-width:500px) {
        width: 90vw;
      }
    }
    
  }
}
</style>
