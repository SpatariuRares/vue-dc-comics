<template>
    <div id="Merchandise">
        <div class="container">
        <div class="row">
            <div class="col" v-for="(image,index) in images" :key="index">
            <img :src="require(`../assets/img/${image.path}`)" alt="">
            <p> {{image.text}}</p>
            </div>
        </div>
        </div>
    </div>
</template>

<script>
import * as images from '@/assets/data/images.js';
export default {
  name: 'Merchandise',
  data(){
    return {
      images:images.footerImages,
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "../style/mixins.scss";
@import "../style/vars.scss";
#Merchandise{
  background-color: $primaryBrand;
  padding: 40px;
  .row{
    display: flex;
    .col{
      width: calc(100% / 5);
      color:white;
      @include center("vertical");
      img{
        width: 50px;
      }
      p{
        margin-left:10px;
        font-size:1rem;
      }
    }
  }
}

</style>
