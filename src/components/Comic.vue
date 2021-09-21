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

<style scope lang="scss">
@import "../style/mixins.scss";
@import "../style/vars.scss";

#Comic {
    div {
        width:100%;
        aspect-ratio: 1/1;
        img{
            width:100%;
            height:100%;
            object-fit: cover;
            object-position: top;
        }
    }
    p{
        color: #fff;
        font-size: 0.8em;
        margin-top: 20px;
    }
}
</style>
