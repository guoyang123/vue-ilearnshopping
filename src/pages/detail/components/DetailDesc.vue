<template>
    <div class="desc_container">
      <div class="wrapper" v-html="detaildata.detail">

    </div>
    </div>
</template>

<script>
    export default {
        name: "DetailDesc",
        props:{
          detaildata:Object
        }
    }
</script>

<style >


       .wrapper .ELazy-loading{
         width:100%
       }
       .wrapper table{
         width: 100%;
       }


</style>
