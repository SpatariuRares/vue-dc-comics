<template>
  <div class="Header">
    <div class="container">
      <div class="row d-flex justify-content-between">
        <div class="col">
          <img src="@/assets/img/dc-logo.png" alt="">
        </div>
        <div class="col">
          <ul>
            <li v-for="(link, index) in links" :key="index">
              <a :class="(link.current) ? 'active' : null" :href="link.url">
                {{ link.text }}
              </a>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import * as Links from '@/assets/data/links.js';
export default {
  name: 'Header',
  data(){
    return {
      links: Links.headerLinks
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "../style/mixins.scss";
@import "../style/vars.scss";
.container{
  .row{
    display:flex;
    justify-content:space-between;
    .col:first-child{
      padding:20px
    }
    .col:last-child{
      @include center("vertical");
      align-items:stretch;
    }
    ul{
      display: flex;
      list-style: none;
      position: relative;
      li{ 
        padding: 0 10px;
        display: flex;
        align-items: stretch;
        a {
          text-decoration: none;
          color:black;
          display: flex;
          align-items: center;
          &:hover,
          &.active{
            color:$primaryBrand;
          }
        }
        .active{
          position: relative;
        }
        & .active::after{
          content:"";
          width:80%;
          height: 10px;
          background-color: $primaryBrand;
          position: absolute;
          bottom: 0;
          left: 10%;
        }
      }
    }
  }
}
</style>
