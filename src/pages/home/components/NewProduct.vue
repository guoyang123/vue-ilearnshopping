<template>
  <div>
    <div class="recommend-title">新品推荐</div>
    <ul>
      <li class="item border-bottom" v-for="(item,index) of newList" :key="index" v-if="index<6">
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.imageHost+item.mainImage"/>
        </div>

        <div class="item-info">
          <p class="item-title">{{item.name}} </p>
          <p class="item-desc">{{item.subtitle}}</p>

        </div>
      </li>
    </ul>
  </div>
</template>

<script>
  export default {
    name: "NewProduct",
    props:{
      newList:Array
    },
    data(){
      return {
        recommendList:[
          {
            id:'001',
            imgUrl:"http://img1.qunarzz.com/sight/source/1505/9e/21df651e19af5d.jpg_r_640x214_3ea5bb38.jpg",
            title:"蓟州滑雪季",
            desc:"欢迎来蓟州滑雪",
            price:'￥50起'
          },
          {
            id:'002',
            imgUrl:"http://img1.qunarzz.com/sight/source/1505/9e/21df651e19af5d.jpg_r_640x214_3ea5bb38.jpg",
            title:"登盘山",
            desc:"欢迎来蓟州滑雪",
            price:'￥80起'
          }, {
            id:'003',
            imgUrl:"http://img1.qunarzz.com/sight/source/1505/9e/21df651e19af5d.jpg_r_640x214_3ea5bb38.jpg",
            title:"黄崖关长城",
            desc:"欢迎来蓟州滑雪",
            price:'￥100起'
          }
        ]
      }
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
    .item-img-wrapper
      height :0
      padding-bottom :34%
      overflow :hidden
      .item-img
        width :100%
    .item-info
      padding .1rem
      .item-title
        line-height: .54rem
        font-size :.32rem
        ellipsis()
      .item-desc
        line-height :.4rem
        color:#ccc
        ellipsis()

</style>

