<template>
  <div id="app">
    <keep-alive>
     <!-- <transition name="slide-fade">-->
        <router-view/>
     <!-- </transition>-->
    </keep-alive>
  </div>


</template>

<script>
    export default {
        name: "App"
    }
</script>

<style lang="stylus" scoped>

  .slide-fade
    position :absolute
    left :0
    right :0
  .slide-fade-enter-active,slide-fade-leave-active
    transition:all 1.2s ease
  /*.slide-fade-leave-active
    transition:all 1.2s cubic-bezier(2.0,0.5,0.8,1.0)*/
  .slide-fade-enter
    left :0
    right :0
    transform :translateX(100%)
  .slide-fade-enter-to,slide-fade-leave
    left :0
    right :0
  .slide-fade-leave-to
    left :0
    right :0
    transform :translateX(-100%)




</style>
