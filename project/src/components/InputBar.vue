<template>
    <div>
        <input type="text" class="input-text" v-model="value" @keydown.enter="handleClickAdd">
        <input type="button" value="Add" class="input2">
    </div>
</template>

<script>
export default {
  name:"InputBar",
  data(){
      return{
          value:""
      };
  },
methods:{
    handleClickAdd(){
        this.$emit("",this.value)
        this.value=""
    }
}
}
</script>

<style>
  .input2{
    background-color:darkorchid;
  }
</style>
