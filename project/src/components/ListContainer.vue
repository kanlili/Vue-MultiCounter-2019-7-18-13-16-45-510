<template>
    <div>
      <ol>
        <li v-for="item in items" :key="item.id " :item="item">
         <input type="checkbox" @click="itemChecked(index)" :checked="item.status">
         <span @dblclick="modify($event)">{{item.value}}</span>
        </li>
      </ol>
    
    </div>
</template>

<script>
export default {
  name:"ListContainer",
  data:function(){
      return{
          item:""
      }
  },
  props:{
        list:{
            type:Array,
            default:()=>[]
        }
    },
    methods: {
         modify(e){
            
        },
    }
};
</script>

<style>

</style>
