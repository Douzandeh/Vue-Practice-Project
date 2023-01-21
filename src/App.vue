<template>
  <h1>{{ title }}</h1>
  <p>Welcome...</p>
  <div v-if="showModal">
      <Modal :header="header" :text="text" theme="sale" @close="changeModal" />
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
      header: "Sign up for a Giveaway",
      text: "Grab the course for half price",
      showModal: false,
    };
  },
  methods: {
    changeModal(){
      this.showModal = !this.showModal
    }
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
