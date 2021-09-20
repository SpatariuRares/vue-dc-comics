<template>
  <div id="Main">
    <div class="container">
    <p>
      Content goes here
    </p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Main',
}
</script>

<style lang="scss">
@import "../style/mixins.scss";
@import "../style/vars.scss";
#Main {
    padding: 50px;
    background-color: $black;
    p{
        color: white;
        font-size:2rem ;
        font-weight: bold;
        &::after{
            content: "<--"
        }
        &::before{
            content: "-->"
        }
    }
}
</style>
