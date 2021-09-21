<template>
  <div id="jumbotron">
      <img src="@/assets/img/jumbotron.jpg" alt="">
  </div>
</template>

<script>
export default {
  name: 'JUmbotron',
}
</script>

<style lang="scss">
@import "../style/mixins.scss";
@import "../style/vars.scss";
#jumbotron{
    width: 100%;
    height: 70vh;
    img{
        width: 100%;
        height: 100%;
        object-fit: cover;
        object-position: top;
    }
}
</style>
