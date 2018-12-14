<template>
 <div>
   <input class="item" v-model="inputvalue"/>
   <button @click="handleClick">提交</button>
   <ul>
    <!-- <li v-for="(item,index) of list" :key="index">{{item}}</li>-->
    <todo-item :content="item" :index="index"
               v-for="(item,index) of list"
               :key="index"
                @delete="handleDelete"></todo-item>
   </ul>
 </div>
</template>

<script>
  import TodoItem from './components/TodoItem'
export default {
 data:function(){
   return {
     inputvalue:"",
     list:[]
   }
 },
  components:{
   'todo-item':TodoItem
  },
  methods:{
    handleClick(){
     this.list.push(this.inputvalue)
      this.inputvalue=""
    },
    handleDelete(index){
      this.list.splice(index)
    }
  }
}
</script>

<style>

</style>
