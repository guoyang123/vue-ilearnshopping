<template>
    <div class="header">
      <div class="header-left">
        <div class="iconfont icon-back">&#xe624;</div>
      </div>
      <router-link to="/city/-1" class="link">
      <div class="header-input"><span class="iconfont">&#xe632;</span><span class="warn">输入要搜索的商品</span></div>
      </router-link>
      <router-link to="/city">
       <!--<div class="header-right"><span class="city">城市</span><span class="iconfont arrow-icon">&#xe64a;</span></div>-->
      </router-link>
    </div>
</template>

<script>
    export default {
        name: "Header"
    }
</script>

<style scoped lang="stylus">
@import '~styles/varibles.styl'
  .header >>> .link
    display :block
    width:100%
    margin-right:.4rem

.header
    display: flex
    height : .86rem
    background:$bgColor
    line-height :.86rem
    color :#ffffff
    .header-left
      width :.64rem
      float:left
      .icon-back
        text-align :center
        font-size: .4rem

    .header-input
      flex:1
      background : #ffffff
      -webkit-border-radius: .1rem
      -moz-border-radius: .1rem
      border-radius: .1rem
      margin-top :.12rem
      margin-left :.1rem
      margin-right:.1rem
      padding-left: .2rem
      height :.64rem
      width:100%
      line-height:.64rem
      color :#ccc
    .header-right
      display:none
      width:1.24rem
      float :right
      text-aligin:center
      font-size :0px
      margin-left: .2rem
      color: #ffffff
      .arrow-icon
        margin-left :-.04rem
        font-size :.24rem
      .city
        font-size :.24rem


</style>
