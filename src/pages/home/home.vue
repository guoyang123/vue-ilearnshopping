<template>
  <div>
    <home-header></home-header>
    <home-swiper :banners="bannerList"></home-swiper>
    <home-icons :rootCategorys="rootCategoryList"></home-icons>
    <home-recommend :hots="hotList" :isshowtitle="true"></home-recommend>
    <new-product :newList="newList"></new-product>
   <!-- <div class="home">home</div>
   <router-link to="/list">列表页</router-link>-->

  </div>
</template>

<script>
  import HomeHeader from "./components/Header"
  import HomeSwiper from './components/Swiper'
  import HomeIcons from './components/Icons'
  import HomeRecommend from './components/Recommend'
  import NewProduct from './components/NewProduct'
  import axios from 'axios'
    export default {
        name: "home",
        components:{
          HomeHeader,HomeSwiper,HomeIcons,HomeRecommend,NewProduct
      },
      data(){
          return {
            bannerList:[],
            hotList:[],
            newList:[],
            rootCategoryList:[]
          }
      },
      mounted() {
        this.getBannerInfo(),
        this.getHotInfo(),
        this.getNewInfo(),
          this.getRootCategoryInfo()

      },
      methods:{
        getBannerInfo(){
            axios.get("http://www.imbession.top/portal/product/detail.do?categoryId=1&is_banner=1")
              .then(this.getBannerInfooSucc)
          },
        getHotInfo(){
          axios.get("http://www.imbession.top/portal/product/detail.do?categoryId=1&is_hot=1")
            .then(this.getHotInfoSucc)
        },
        getNewInfo(){
          //http://www.imbession.top/portal/product/list.do?categoryId=1&is_banner=1&pageNum=1&pageSize=6
          //
          axios.get("http://www.imbession.top/portal/product/detail.do?categoryId=1&is_banner=1")
            .then(this.getNewInfoSucc)
        },
        getRootCategoryInfo(){
            axios.get(" http://www.imbession.top/manage/category/get_category.do?categoryId=0")
              .then(this.getRootCategoryInfoSucc)
        },
        getBannerInfooSucc(res){
            //接口返回的数据
            res=res.data
            if(res.status==0 && res.data){
              const data=res.data
              this.bannerList=data
              console.log(this.bannerList)
            }

          },
        getHotInfoSucc(res){
          //接口返回的数据
          res=res.data
          if(res.status==0 && res.data){
            const data=res.data
            this.hotList=data
            console.log(this.hotList)
          }
        },
        getNewInfoSucc(res){
          //接口返回的数据
          res=res.data
          if(res.status==0 && res.data){
            const data=res.data
            this.newList=data
            console.log(this.newList)
          }
        },
        getRootCategoryInfoSucc(res){
        //接口返回的数据
        res=res.data
        if(res.status==0 && res.data){
          const data=res.data
          this.rootCategoryList=data
          console.log(this.rootCategoryList)
        }
  },
      }
    }
</script>

<style scoped>


</style>
