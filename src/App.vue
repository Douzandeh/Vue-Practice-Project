<template>
  <h1>{{ title }}</h1>
  <p>Welcome...</p>
  <div v-if="showModal">
    <Modal theme="sale" @close="changeModal">
      <h1>OpenCode Giveaway</h1>
      <p>Grab the course for half price</p>
      <template v-slot:links>
        <a href="#">Sign up</a>
        <a href="#">More info</a>
      </template>
    </Modal>
  </div>
  <button @click.alt="changeModal">Show Modal (alt + click right)</button>
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: { Modal },
  data() {
    return {
      title: "My vue App",
      showModal: false,
    };
  },
  methods: {
    changeModal() {
      this.showModal = !this.showModal;
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
  border-bottom: solid 1px #ccc;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
