<template>
  <div ref="wrapper">
    <div>
    <div    class="search">
      <input class="search-input"  v-model="keyword" type="text" placeholder="输入商品名"/>

    </div>
    <div class="search-content">
      <home-recommend :hots="list" :isshowtitle="false"></home-recommend>
      <div class="no_content" v-if="isshowcontent">无数据</div>
    </div>
    </div>
  </div>

</template>

<script>
  import BScroll from 'better-scroll'
  import HomeRecommend from '@/pages/home/components/Recommend'
  import  axios from 'axios'
    export default {
        name: "CitySearch",
      props:{
          categoryId:String
      },
        data(){
          return {
            keyword:"",
            timer:null,
            list:[],
            isshowcontent:true
          }
        },
      components:{
        HomeRecommend
      },
      activated(){
        this.keyword=null
         this.list=[]
        this.isshowcontent=true
        this.getSearchProductInfo()
      },
      watch:{
        keyword(){
          if(!this.keyword){
            this.list=[]
            return
          }
          //100ms后发起网络请求
          if(this.timer){
            clearTimeout(this.timer)
          }
          this.timer=setTimeout(()=>{
            //请求网络数据
            this.getSearchProductInfo()
          },100)

        }
      },

      methods:{
        getSearchProductInfo(){
          axios.get("http://www.imbession.top/portal/product/list.do",{
            params:{
              keyword:this.keyword,
              categoryId:this.categoryId==-1?null:this.categoryId
            }
          } )
            .then(this.getSearchProductInfoSucc)
        },
        getSearchProductInfoSucc(res){
          //接口返回的数据
          res=res.data
          if(res.status==0 && res.data){
            const data=res.data.list
            this.list=data
            console.log(this.list.length)
            if(this.list.length>0){
              this.isshowcontent=false
            }else{
              this.isshowcontent=true
            }

            console.log(this.isshowcontent)
          }
        }
      },
      mounted(){
          //this.scroll=new BScroll(this.$refs.wrapper)
      }


    }
</script>

<style lang="stylus" scoped>
  @import "~styles/varibles.styl"

  .search
    height:.72rem
    background:$bgColor
    padding:0.1rem
    .search-input
      height :.62rem
      line-height :.62rem
      width :100%
      text-align :center
      border-radius :.06rem
      color:#666
      box-sizing :border-box
      padding :0 .1rem
  .search-content
    overflow :hidden
    top :1.58rem
    left :0
    right:0
    bottom :0
    z-index:1
    .no_content
      background :#ccc
      height :.4rem
      line-height :.4rem
      padding-left :.2rem
      color :#ffffff

</style>
