<template>
  <div id="Main">
    <div class="container position-relative">
      <div id="Current" class="button">
        <p>CURRENT SERIES </p>
      </div>
      <ul>
        <Comic 
            v-for="(comic, index) in comics" 
            :key="index"
            :comic="comic"
            />
      </ul>
      <div class="text_center">
        <span id="Load" class="button">LOAD MORE</span>
      </div>
    </div>
  </div>
</template>

<script>
import dataComic from '@/assets/data/dc-comics.js';
import Comic from '@/components/Comic.vue'
export default {
  name: 'Main',
  components: {
    Comic
    },
    data(){
    return {
      comics:dataComic
    }
  }
}
</script>

<style lang="scss">
@import "../style/mixins.scss";
@import "../style/vars.scss";
#Main {
    padding: 50px;
    background-color: $black;
    .button{
      color: #fff;
      background-color:$primaryBrand;
      font-weight: 900; 
      padding: 10px;
    }
    #Current {
      position: absolute;
      font-size:1.5em;
      top: calc(-50px + -20px);
    }
    #Load{
      display: inline-block;
    }
    ul{
      display: flex;
      flex-wrap: wrap;
      li{
        width: calc((100% / 6) - 20px);
        margin: 10px;
      }
    }
}
</style>
