<template>
    <div>
        <InputBar @push="onPushTodoItem($event)"></InputBar>
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
  computed:{
     list(){
        switch (this.status) {
        case "ACTIVE":
          return this.items.filter(item => item.active === true);
        case "COMPLETE":
          return this.items.filter(item => item.active === false);
        case "ALL":
        default:
          return this.items;
      }
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
