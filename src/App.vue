<template>
  <h1>{{ title }}</h1>
  <p>Welcome...</p>
  <teleport to=".modals" v-if="showModal">
    <!-- <Modal :header="header" :text="text" theme="sale" @close="toggleModal"/> -->
    <Modal theme="sale" @close="toggleModal">
      <template v-slot:links>
        <a href="#">sign up now</a>
        <a href="#">more info</a>
      </template>
      <h1>Ninja Givaway!</h1>
      <p>Grab your ninja swag for half price!</p>
    </Modal>
  </teleport>
  <button @click.alt="toggleModal">open modal (alt)</button>
  <!-- <input type="text" ref="name">
  <button @click="handleClick">Click me</button> -->
  <teleport to=".modals" v-if="showModalTwo">
    <Modal @close="toggleModalTwo">
      <template v-slot:biggy>
          <h1>Biggy</h1>
          <p>This is new and shiny</p>
      </template>
    </Modal>
  </teleport>
  <button @click="toggleModalTwo">open this new modal</button>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: { Modal },
  data () {
    return {
      title: 'My First Vue App :)',
      // header: 'Sign up for the Giveaway',
      // text: 'Grab your snack for half price!',
      showModal: false,
      showModalTwo: false
    }
  },
  methods: {
    // handleClick() {
    //   console.log(this.$refs.name)
    //   this.$refs.name.classList.add('active')
    //   this.$refs.name.focus()
    // }
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
#app, .modals {
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


<!-- GITHUB LESSON 28 -->