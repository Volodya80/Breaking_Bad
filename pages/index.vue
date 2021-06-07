<template>
  <div class="container">
    <img src="@/assets/img/index_img.jpg" class="img-fluid" alt="picture">
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
  //text-align: center;
  
  background-image: url('@/assets/img/index_img.jpg');
  
  background-size: cover;
  background-repeat: no-repeat;
}
.mycontainer:after {
/*   content: "";
  display: block;
  width: 100%;
  height: 100%;
  position: absolute;
  top: 0;
  left: 0;
  background: transparent;
  background-image: linear-gradient(45deg rgba(0,0,0,0) rgba(0,0,0,1));
  opacity: 0.8; */
}


</style>
