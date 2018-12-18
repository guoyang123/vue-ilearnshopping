<template>
  <div >
    <div >
    <div class="recommend-title">热销推荐</div>
    <ul>
      <router-link
        tag="li"
        class="item border-bottom"
        v-for="(item,index) of hots"
        :key="index"
         :to="'/detail/'+item.id">
         <img class="item-img" :src="item.imageHost+item.mainImage"/>
         <div class="item-info">
           <p class="item-title">{{item.name}} </p>
           <p class="item-desc">{{item.subtitle}}</p>
           <p class="item-price">￥{{item.price}}</p>
           <!--<button class="item-button">查看详情</button>-->
         </div>
      </router-link>
    </ul>
    </div>
  </div>
</template>

<script>

    export default {
        name: "HomeRecommend",
        props:{
          hots:Array
        }
    }
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl'
  .recommend-title
   line-height :.8rem
   background :#eee
   margin-top:.2rem
   text-indent:.2rem
  .item
    overflow :hidden
    height:1.9rem
    display :flex
    .item-img
     width :1.7rem
     height :1.7rem
     padding :.1rem
    .item-info
      flex:1
      padding .1rem
      min-width:0
      .item-title
        line-height: .54rem
        font-size :.32rem
        ellipsis()
      .item-desc
        line-height :.4rem
        color:#ccc
        ellipsis()
      .item-price
        margin-top:.16rem
        line-height :.32rem
        font-size :.32rem
        color:red
      .item-button
        line-height :.44rem
        margin-top:.16rem
        background :#ff9300
        padding :0.2rem
        border-radius :.06rem
        color :#ffffff
</style>
