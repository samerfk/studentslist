<template>
  <div id="app">    
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <input type="button" class="lbtn" value="Add student" @click="addStudent" />
    <Students v-bind:mystudents="mystudents" 
      v-on:del-student="deleteStudent" />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Students from './components/Students'

export default {
  name: 'App',
  components: {
    HelloWorld, Students
  },

  data(){
    return{
      mystudents : [
        {
          id:1,
          name:'sarah',
          graduated: true
        },
        {
          id:2,
          name:'john',
          graduated: false
        },
        {
          id:3,
          name:'sally',
          graduated: true
        }
      ]
    }
  },
  methods:{
    deleteStudent(id){
      this.mystudents = this.mystudents.filter(elm => elm.id != id )
    },
    addStudent(){
      this.mystudents.push({id:4, name:'Mike', graduated:true})
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.lbtn{
    background-color: red;
    border-radius: 90%;
    width: 95px;
    height:25px;
    
}
</style>
