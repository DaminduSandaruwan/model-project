<template>
  <!-- <h1>Home Page</h1> -->
  <h1>{{title}}</h1>
  <!-- <input type="text" ref="name">  -->
  <!-- <button @click="handleClick">Click Me</button> -->
  <p>Welcome...   </p>
  <teleport to="#modals" v-if="showModal">
    <Modal theme="sale" @close="toggleModal">
      <template v-slot:links>
        <a href="#">Sign up now</a> <br>
        <a href="#">more info</a>
      </template>
      <h1>Main Title</h1>
      <P> This is an paragraph</P>
    </Modal>
  </teleport>
  <div v-if="showModalTwo">
    <Modal @close="toggleModalTwo">
      <h1>Sign up to news</h1>
      <P> for updates and promo code</P>
    </Modal> 
  </div>
  <button @click="toggleModal">Open Model</button>
  <button @click="toggleModalTwo">Open Model</button>
  
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
      showModalTwo: false,
    }    
  },
  methods: {
    handleClick(){
      console.log(this.$refs.name);
      this.$refs.name.classList.add('active');
    },
    toggleModal(){
      this.showModal = !this.showModal
    },
    toggleModalTwo(){
      this.showModalTwo = !this.showModalTwo
    },
  },
}
</script>

<style>
#app, #modals{
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

