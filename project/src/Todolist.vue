<template>
  <div id="app">
     <Header></Header>
     <Body :list="list" @push="onPushTodoItem"> </Body>
     <Footer></Footer>
  </div>
</template>

<script>
import Header from "./components/Header.vue"
import Body from "./components/Body.vue"
import Footer from "./components/Footer.vue"

export default {
  name: 'app',
  components:{
    Header,
    Body,
    Footer
  },
  data(){
    return{
      list:[]
    }; 
  },
  methods:{
  onPushTodoItem(value){
     const item={
       value,
       finished:false,
     }
     this.list.push(item);
  }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
