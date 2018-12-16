<template>
    <div>
       <div class="name-info border-bottom">
         <p class="name">{{detailinfo.name}}</p>
         <p class="price_container">价格:<span class="price">￥{{detailinfo.price}}</span></p>
       </div>
    </div>
</template>

<script>
    export default {
        name: "DetailInfo",
        props:{
          detailinfo:Object
        }
    }
</script>

<style scoped lang="stylus">
  .name-info
    margin :.2rem
    .name
      font-size :.3rem
      font-weight :bold
    .price_container
      margin-top:.2rem
      font-size :.3rem
      font-weight :bold
      padding-bottom :.2rem
      .price
        color :red

</style>
