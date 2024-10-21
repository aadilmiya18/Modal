<template>
  <h1>{{ title }}</h1>
  <!-- <input type="text" ref="name" />
  <button @click="handleEvents">click me</button> -->

  <Teleport to=".modals" v-if="showModal">
    <Modal
      :header="header"
      :text="text"
      :array="array"
      theme="sale"
      @close="toggleModal"
    >
      <h2>Slotts</h2>
      <p>this is a slot</p>

      <template v-slot:links>
        <a href="#">Sign up</a>
        <a href="#">More info</a>
      </template>
    </Modal>
  </Teleport>
  <button @click="toggleModal">Open Modal</button>
  <br />
  <br />

  <div>

  </div>

  <Teleport to=".modals" v-if="showModalTwo" >

    <Modal @close="toggleModalTwo">
      <h1>Sign up to the newspaper</h1>
      <p>For updates and promo codes</p>
    </Modal>


  </Teleport>
  
  <button @click="toggleModalTwo">Open Model 2</button>
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: { Modal },
  data() {
    return {
      title: "My first vue app",
      header: "Aadil Miya",
      text: "texttttt",
      array: ["aadil", 18],
      showModal: false,
      showModalTwo: false
    };
  },
  methods: {
    handleEvents() {
      console.log(this.$refs.name);
      this.$refs.name.classList.add("active");
      this.$refs.name.focus();
    },
    toggleModal() {
      this.showModal = !this.showModal;
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo;
    },
  },
};
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
  background-color: yellowgreen;
}
</style>
