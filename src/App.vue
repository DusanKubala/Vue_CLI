<template>
  <h1>{{ title }}</h1>
  <p>
    Welcome...
  </p>
  <div v-if="modalShow">
    <Modal :header="header" :text="text" theme="sale" @close="modalToggle()"/>
  </div>
  <button @click="modalToggle()">Toggle modal</button>
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
      modalShow: false
    }
  },
  methods:{
    modalToggle(){
      this.modalShow = !this.modalShow
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
</style>
