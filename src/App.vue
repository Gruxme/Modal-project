<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <br>
  <h1>{{ title }}</h1>
  <p>Welcome...</p>
  <teleport to="#modals" v-if="showModal">
    <Modal theme="sale" @close="toggleModal">
      <template v-slot:links>
        <a href="#">Sign up now</a>
        <a href="#">more info</a>
      </template>
      <h1>Sign Up!</h1>
      <p>Grab your merch now!</p>
    </Modal>
  </teleport>
  <teleport to="#modals" v-if="showModalTwo">
    <Modal @close="toggleModalTwo">
       <template v-slot:links>
        <a href="#">Sign In</a>
        <a href="#">More Info</a>
      </template>
      <h1>Sign In and get your free ticket!</h1>
      <p>*One month free subscription ticket</p>
    </Modal>
  </teleport>
  <button @click="toggleModal">Open Modal</button>
  <button @click="toggleModalTwo">Open Modal Two</button>
</template>

<script>
import Modal from './components/Modal.vue'
export default {
  name: 'App',
  components: {
    Modal
  },
  data() {
    return {
      title: 'My first Vue app',
      showModal: false,
      showModalTwo: false
    };
  },
  methods: {
    toggleModal(){
      this.showModal = !this.showModal;
    },
    toggleModalTwo(){
      this.showModalTwo = !this.showModalTwo;
    }
  }
}
</script>

<style>
#app, #modals {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1 {
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
