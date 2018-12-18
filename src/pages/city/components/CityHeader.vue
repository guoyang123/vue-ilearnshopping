<template>
    <div class="header">
       商品列表
      <router-link  to="/">
      <div class="header-left"><div class="iconfont header-back">&#xe624;</div></div>
      </router-link>
    </div>
</template>

<script>
    export default {
        name: "CityHeader"
    }
</script>

<style  lang="stylus" scoped>
  @import "~styles/varibles.styl"
 .header
   position :relative
   overflow :hidden
   height :$haderHeight
   line-height :$haderHeight
   text-align :center
   color :#ffffff
   background : $bgColor
   font-size: .32rem
   .header-back
     position :absolute
     left :0
     top:0
     width :.64rem
     text-align :center
     font-size :.4rem
     color :#ffffff



</style>
