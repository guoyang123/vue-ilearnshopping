<template>
    <div class="icons">
      <swiper :options="swiperOptions">
        <swiper-slide v-for="(page,index1) of pages" :key="index1">
         <router-link tag="div"
                      class="icon" v-for="(item,index) of page"
                      :key="index"
                      :to="'/city/'+item.id">
           <div class="icon-img">
             <img class="icon-img-content" src="http://img1.qunarzz.com/piao/fusion/1611/54/ace00878a52d9702.png"/>
           </div>
           <p class="icon-desc">{{item.name}}</p>
         </router-link>
        </swiper-slide>
      </swiper>

    </div>
</template>

<script>
    export default {
        name: "HomeIcons",
        props:{
          rootCategorys:Array
        },
        data(){
          return {
            swiperOptions:{
              pagination:'.swiper-pagination',
              autoplay:false
            },
            iconList:[
              {id:'001',imgUrl:'http://img1.qunarzz.com/piao/fusion/1611/54/ace00878a52d9702.png',desc:'景点门票'},
              {id:'002',imgUrl:'http://img1.qunarzz.com/piao/fusion/1611/54/ace00878a52d9702.png',desc:'滑雪季'},
              {id:'003',imgUrl:'http://img1.qunarzz.com/piao/fusion/1611/54/ace00878a52d9702.png',desc:'泡温泉'},
              {id:'004',imgUrl:'http://img1.qunarzz.com/piao/fusion/1611/54/ace00878a52d9702.png',desc:'动植圆'},
              {id:'005',imgUrl:'http://img1.qunarzz.com/piao/fusion/1611/54/ace00878a52d9702.png',desc:'一日游'},
              {id:'006',imgUrl:'http://img1.qunarzz.com/piao/fusion/1611/54/ace00878a52d9702.png',desc:'周边游'},
              {id:'007',imgUrl:'http://img1.qunarzz.com/piao/fusion/1611/54/ace00878a52d9702.png',desc:'蓟州滑雪'},
              {id:'008',imgUrl:'http://img1.qunarzz.com/piao/fusion/1611/54/ace00878a52d9702.png',desc:'游乐场'},
              {id:'009',imgUrl:'http://img1.qunarzz.com/piao/fusion/1611/54/ace00878a52d9702.png',desc:'天津旅游'},
            ]
          }
        },
      computed:{
          pages(){
            const pages=[]
            this.rootCategorys.forEach((item,index)=>{
              //该元素在第几页
              const page=Math.floor(index/8)
              if(!pages[page]){
                pages[page]=[]
              }
              pages[page].push(item)
            })
            return pages
          }
      }
    }
</script>

<style scoped lang="stylus">
  @import '~styles/varibles.styl'
  @import '~styles/mixins.styl'
 .icons >>> .swiper-container
   height:0
   padding-bottom:50%
  .icons
    margin-top: .1rem
   .icon
     position :relative
     overflow:hidden
     float :left
     width :25%
     height :0
     padding-bottom :25%
     .icon-img
       position :absolute
       top :0
       left :0
       right:0
       bottom:.44rem
       box-sizing :border-box
       padding:.1rem
       .icon-img-content
         display :block
         margin:0 auto
         height:100%
   .icon-desc
     position :absolute
     left :0
     right:0
     bottom:0
     height :.44rem
     line-height :.44rem
     color :$darkTextColor
     text-align :center
     ellipsis()
</style>
