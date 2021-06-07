<template>
  <div class="container">

  </div>
</template>

<script>
export default {}
</script>

<style>
.container {
  width: 100%;
  height: 100%;

  display: inline-block;
  text-align: center;
  
  background-image: url('@/assets/img/index_img.jpg');
  
  background-size: cover;
  background-repeat: no-repeat;
}
.container:after {
  content: "";
  display: block;
  width: 100%;
  height: 100%;
  position: absolute;
  top: 0;
  left: 0;
  background: transparent;
  background-image: linear-gradient(45deg rgba(0,0,0,0) rgba(0,0,0,1));
  opacity: 0.8;
}

.title {
  font-family:
    'Quicksand',
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
