<template>
 <li @click="handleClick" class="item">{{content}}</li>
</template>

<script>
export default {
 props:['content','index'],
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  methods:{
   handleClick(index){
      this.$emit('delete',this.index)
   }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style >
.item{
  color:green;
}
</style>
