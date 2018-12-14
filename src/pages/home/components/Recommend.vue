<template>
  <div>
    <div class="recommend-title">热销推荐</div>
    <ul>
      <li class="item border-bottom" v-for="(item,index) of recommendList" :key="index">
         <img class="item-img" :src="item.imgUrl"/>
         <div class="item-info">
           <p class="item-title">{{item.title}} </p>
           <p class="item-desc">{{item.desc}}</p>
           <p class="item-price">{{item.price}}</p>
           <!--<button class="item-button">查看详情</button>-->
         </div>
      </li>
    </ul>
  </div>
</template>

<script>
    export default {
        name: "HomeRecommend",
      data(){
          return {
            recommendList:[
              {
                id:'001',
                imgUrl:"http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_200x200_1bc99086.jpg",
                title:"蓟州滑雪季",
                desc:"欢迎来蓟州滑雪",
                price:'￥50起'
              },
              {
                id:'002',
                imgUrl:"http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_200x200_1bc99086.jpg",
                title:"登盘山",
                desc:"欢迎来蓟州滑雪",
                price:'￥80起'
              }, {
                id:'003',
                imgUrl:"http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_200x200_1bc99086.jpg",
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
