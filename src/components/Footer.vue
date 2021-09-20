<template>
  <div class="Footer">
    <Merchandise />
    <div id="list">
      <div class="container">
        <div class="d-flex position-relative">
          <div class="row">
            <div>
              <ul>
                <li class="title"> <h3>DC COMICS</h3></li>
                <li v-for="(link,index) in links[0].links" :key="index"><a :href="link.url">{{link.text}}</a></li>
              </ul>
              <ul>
                <li class="title"><h3>SHOP</h3></li>
                <li v-for="(link,index) in links[1].links" :key="index"><a :href="link.url">{{link.text}}</a></li>
              </ul>
            </div>
            <div>
              <ul>
                <li class="title"><h3>DC</h3></li>
                <li v-for="(link,index) in links[2].links" :key="index"><a :href="link.url">{{link.text}}</a></li>
              </ul>
            </div>
            <div>
              <ul>
                <li class="title"> <h3> SITES</h3></li>
                <li v-for="(link,index) in links[3].links" :key="index"><a :href="link.url">{{link.text}}</a></li>
              </ul>
            </div>
          </div>
          <img src="@/assets/img/dc-logo-bg.png" alt="">
        </div>
      </div>
    </div>
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
  </div>
</template>

<script>
import Merchandise from '@/components/Merchandise.vue'
import * as Links from '@/assets/data/links.js';
import * as images from '@/assets/data/images.js';
export default {
  name: 'Footer',
  components:{
    Merchandise
  },
  data(){
    return {
      links: Links.footerLinks,
      images:images.footerImages,
      socials: images.footerSocials,
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "../style/mixins.scss";
@import "../style/vars.scss";
.Footer{
  overflow: hidden;
}
.d-flex{
  display:flex;
}
.position-relative{
  position: relative;
}
.justify-content-between{
  justify-content: space-between
}

#list{
  background-image: url("../assets/img/footer-bg.jpg");
  background-size: cover;
  padding: 30px;
  overflow: hidden;
  .row{
    display:flex;
    .col{
      @include center("vertical");
      align-items:stretch;
    }
    ul{
      margin-right: 20px;
      list-style: none;
      position: relative;
      .title{
        color:white;
        padding: 20px 0;
        font-weight: 700;
        text-transform: uppercase;
      }
      li{ 
        a {
          text-transform: capitalize;
          text-decoration: none;
          color:gray;
        }
      }
    }
  }
  img {
    position: absolute;
    right: 0;
    top: -117px;
  }
}
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
