<template>
  <div id="social">
      <div class="container">
          <div class="d-flex justify-content-between">
              <div id="sing">SING-UP NOW</div>
              <div id="follow">
              <p>follow us</p>
              <div v-for="(social,index) in socials" :key="index">
                  <img :src="require(`../assets/img/${social.path}`)" alt="">
              </div>
              </div>
          </div>
      </div>
  </div>
</template>

<script>

import * as images from '@/assets/data/images.js';
export default {
  name: 'Socials',
  data(){
    return {
      socials: images.footerSocials,
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "../style/mixins.scss";
@import "../style/vars.scss";



#social{
  background-color:#303030;
  padding: 30px ;
  #sing{
    padding: 10px;
    border: 2px solid $primaryBrand;
    color:white;
    font-weight: 700;
  }
  #follow{
    @include center("vertical");
    div{
      margin: 0 5px;
    }
    p{
      color:$primaryBrand;
      text-transform:uppercase;
      font-weight: 700;
      padding: 0 20px;
    }
  }
}
</style>
