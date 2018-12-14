<template>
  <div>
    <home-header></home-header>
    <div class="home">home</div>
   <router-link to="/list">列表页</router-link>

  </div>
</template>

<script>
  import HomeHeader from "./components/Header"
    export default {
        name: "home",
        components:{
          HomeHeader
      }
    }
</script>

<style scoped>

  .home{
    font-size: 50px;
  }
</style>
