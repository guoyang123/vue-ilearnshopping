<template>
    <div>
      <detail-banner :detailheader="detail"></detail-banner>
      <detail-header></detail-header>
      <detail-info :detailinfo="detail"></detail-info>
      <detail-desc :detaildata="detail"> </detail-desc>
    </div>
</template>

<script>
  import DetailBanner from './components/DetailBanner'
  import DetailHeader from './components/DetailHeader'
  import DetailDesc from './components/DetailDesc'
  import DetailInfo from './components/DetailInfo'
  import axios from 'axios'

    export default {
        name: "Detail",
        components:{
          DetailBanner,
          DetailHeader,
          DetailDesc,
          DetailInfo
        },
        mounted() {
          this.getDetailInfo()
        },
       activated(){
         this.getDetailInfo()
       },
       data(){
          return {
           detail:{}
          }
       },
      methods:{
        getDetailInfo(){
          axios.get("http://www.imbession.top/portal/product/detail.do",{
            params:{
              productId:this.$route.params.id
            }
          } )
            .then(this.getDetailInfoSucc)
        },
        getDetailInfoSucc(res){
          res=res.data
          if(res.status==0&&res.data){
            this.detail=res.data
             //console.log(this.detail)
          }
        }
      }
    }
</script>

<style scoped lang="stylus">



</style>
