<template>
  <li id="Comic">
      <div>
        <img :src="comic.thumb" alt="">
      </div>
    <p>{{comic.series}}</p>
  </li>
</template>

<script>

export default {
  name: 'Comic',
  props:[
    "comic",
  ]
}
</script>

<style lang="scss">
@import "../style/mixins.scss";
@import "../style/vars.scss";
div {
    width:100%;
    img{
        width:100%;
        height:100%;
        object-fit: cover;
    
    }
}
p{
    color: #fff;
}
</style>
