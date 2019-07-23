<template>
    <div>
      <button v-on:click="selectAllItems">All</button>
      <button  v-on:click="selectActiveItems">Active</button>
      <button v-on:click="selectCompletedItems">Copleted </button>
    </div>
</template>

<script>
import bus from '../assets/Bus.js'
export default {
  name:"Footer",
  data: () => {
      return {
        status: ""
      }
    },
    methods:{
        selectAllItems:function(){
            this.status='All'
            bus.$emit("status", this.status)
        },
        selectActiveItems:function(){
            this.status='Active'
            bus.$emit("status", this.status)
        },
        selectCompletedItems:function(){
            this.status='Completed'
            bus.$emit("status", this.status)
        },
    }
}
</script>

<style>

</style>
