<template>
  <div id="Main">
    <div class="container">
      <ul>
        <Comic 
            v-for="(comic, index) in comics" 
            :key="index"
            :comic="comic"
            />
      </ul>
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
    ul{
      display: flex;
      flex-wrap: wrap;
      li{
        width: calc((100% / 6) - 40px);
        margin: 10px;
      }
    }
}
</style>
