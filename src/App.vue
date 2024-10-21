<template>
  <h1>{{ title}}</h1>
  <p>Welcome...</p>
  <div v-if="showModal">
    <Modal theme="" @close="toggleModal">
      <template v-slot:links>
        <a href="#">sign up now</a>
        <a href="#">more info</a>
      </template>
        <h1>Ninja Giveaway!</h1>
        <p>Grab your ninja swag for half price!</p>
    </Modal>
  </div>

  <div v-if="showModalTwo">
    <Modal @close="toggleModal">
       <h1>Sign up to the newsletter</h1>
       <p>For updates and promo codes!</p>
    </Modal>
  </div> 
  <button @click.alt="toggleModal">open modal (alt)</button>
  <button @click="toggleModalTwo">open modal 2</button>
</template>

<script>
// Challenge
// - create an extra button to open a different model
// - use the same modal component but pass in a different template (slot)
// - use a diferente method (e.g. toggleModaltwo and data (e.g. showModalTwo)

import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: { Modal },
  data() {
    return {
      title: 'My First Vue App :)',
      showModal: false,
      showModalTwo: false,
    }
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo
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
h1 {
  border-bottom: .0625rem solid #ddd;
  display: inline-block;
  padding-bottom: .625rem;
}
</style>
