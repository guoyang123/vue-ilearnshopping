<template>
    <div>
      <detail-banner :detailheader="detail"></detail-banner>
    </div>
</template>

<script>
  import DetailBanner from './components/DetailBanner'
  import axios from 'axios'
    export default {
        name: "Detail",
        components:{
          DetailBanner
        },
        mounted() {
          this.getDetailInfo()
        },
       data(){
          return {
           detail:{}
          }
       },
      methods:{
        getDetailInfo(){
          axios.get("http://www.imbession.top/portal/product/detail.do?productId=9521")
            .then(this.getDetailInfoSucc)
        },
        getDetailInfoSucc(res){
          res=res.data
          if(res.status==0&&res.data){
            this.detail=res.data

          }
        }
      }
    }
</script>

<style scoped>

</style>
