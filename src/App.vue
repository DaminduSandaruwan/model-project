<template>
  <!-- <h1>Home Page</h1> -->
  <h1>{{title}}</h1>
  <!-- <input type="text" ref="name">  -->
  <!-- <button @click="handleClick">Click Me</button> -->
  <p>Welcome...   </p>
  <div v-if="showModal">
    <Modal :header= "header" :text = "text" theme="sale"/>  
  </div>
  <button @click="toggleModal">Open Model</button>
  
</template>

<script>

import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components:{Modal},
  data (){
    return{
      title : 'My First Vue App',
      header : 'Sign up to the giveway',
      text : 'This is a sample text',
      showModal: false,
    }    
  },
  methods: {
    handleClick(){
      console.log(this.$refs.name);
      this.$refs.name.classList.add('active');
    },
    toggleModal(){
      this.showModal = !this.showModal
    }
  },
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
h1{
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>

