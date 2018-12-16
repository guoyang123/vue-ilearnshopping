<template>
  <div>
    <div class="header-abs" v-show="!showHeader">
      <router-link tag="div" to="/" class="iconfont header-abs-back">&#xe624;</router-link>
    </div>
    <div class="header-fixed" v-show="showHeader">
      <router-link tag="div" to="/" class="iconfont header-abs-back">&#xe624;</router-link>
      商品详细
    </div>
  </div>

</template>

<script>
    export default {
        name: "DetailHeader",
        data(){
          return {
            showHeader:false
          }
        },
      methods:{
          handleScroll(){
           const top= document.documentElement.scrollTop

            if(top>60){
              this.showHeader=true
            }else{
              this.showHeader=false
            }
          }
      },
      activated() {
        window.addEventListener('scroll',this.handleScroll)
      },
      deactivated() {
        window.removeEventListener('scroll',this.handleScroll)
      }
    }
</script>

<style lang="stylus" scoped>
 @import "~styles/varibles.styl"
  .header-abs
    position :absolute
    top:.2rem
    left:.2rem
    width :.8rem
    height :.8rem
    line-height :.8rem
    border-radius :.4rem
    background :rgba(0,0,0,.8)
    text-align :center
    .header-abs-back
      color :#ffffff
      font-size :.4rem
   .header-fixed
     position :fixed
     top:0
     left:0
     right :0
     height :$headerHeight
     line-height :$headerHeight
     text-align :center
     background :$bgColor
     font-size :.32rem
     color: #ffffff
     .header-abs-back
       position :absolute
       top:0
       left:0
       width:.64rem
       text-align :center
       font-size:.4rem


</style>
