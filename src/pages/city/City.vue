<template>
    <div>
       <city-header></city-header>
      <city-search :categoryId="this.$route.params.id"></city-search>
    </div>
</template>

<script>
  import  CityHeader from './components/CityHeader'
  import  CitySearch from './components/CitySearch'
    export default {
        name: "City",
      data(){
      return {

      }
      },
        components:{
          CityHeader,
          CitySearch
        }
    }
</script>

<style scoped>

</style>
