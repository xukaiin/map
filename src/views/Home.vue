<template>
  <div class="home">
    <div v-for="(item, index) in items" :key="index">
      <span>{{item.name}}</span>
      <p>{{item.id}}</p>
      <p v-if="item.sex">{{item.sex}}</p>
    </div>
    <div class="imgCont"></div>
    <button @click="handleClick">添加数据</button>
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  components: {
    HelloWorld
  },
  data() {
    return {
      items:[
        {name: "one", id: "first"},
        {name: "two", id: "second"}
        ]
    }
  },
  computed:{
    checkStatus(){
      console.log(this.checkStatus);
    }
  },
  created(){
    console.log(this.items);
  },
  methods:{
    handleClick(){
      this.$set(this.items[1], "sex" , "women")
    }
  }
}
</script>
<style scoped>
 .imgCont{
   height: 500px;
   width: 500px;
   background:red url("../assets/logo.png") no-repeat center right /50px 50px;
 }
</style>
