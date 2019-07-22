<template>
    <div>
        <InputBar @push="onPushTodoItem"></InputBar>
        <ListContainer :list="list"></ListContainer>
    </div>
</template>

<script>
import InputBar from "./InputBar.vue"
import ListContainer from "./ListContainer.vue"
export default {
  name:"Body",
  components:{
      InputBar,
      ListContainer
  },
  props:{
   list:{
       type:Array,
       default:()=>[]
   }
  },
  method:{
  onPushTodoItem(payload){
      this.$emit("push",payload);
  }
  }

}
</script>

<style>

</style>
