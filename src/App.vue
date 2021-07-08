<template>
  <h1>{{ title }}</h1>
  <p>
    Welcome...
  </p>
  <div v-if="modalShow">
    <Modal  theme="" @close="modalToggle()">
      <template v-slot:links>
        <a href="#">sign up now</a>
        <a href="#">more info</a>
      </template>
      <h1>Title modal</h1>
      <p>Modal content</p>  
    </Modal>
  </div>
  <button @click="modalToggle()">Toggle modal 1</button>

  <div v-if="modalShow2">
   <Modal @close="modalToggle2()">
     <template v-slot:links>
        <a href="#">sign up</a>
        <a href="#">sign out</a>
      </template>
   </Modal>
  </div>
  <button @click="modalToggle2()">Toggle model 2</button>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: { Modal },
  data() {
    return {
      title: 'My first component created by Vue.js',
      header: 'Hello world props',
      text: 'Modal content',
      modalShow: false,
      modalShow2: false
    }
  },
  methods:{
    modalToggle(){
      this.modalShow = !this.modalShow
    },
    modalToggle2(){
      this.modalShow2 = !this.modalShow2
    }
  }
}
</script>

<style >
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}


</style>
