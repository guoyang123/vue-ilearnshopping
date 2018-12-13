<template>
 <div>
   <input v-model="inputvalue"/>
   <button @click="handleClick">提交</button>
   <ul>
     <li>1</li>
     <li>2</li>
   </ul>
 </div>
</template>

<script>
export default {
 data:function(){
   return {
     inputvalue:"",
     list:[]
   }
 },
  methods:{
    handleClick(){
     this.list.push(this.inputvalue)
      this.inputvalue=""
    }
  }
}
</script>

<style>

</style>
