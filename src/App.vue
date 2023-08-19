<template>
  <h1>{{ title }}</h1>
  <p>Welcome</p>
  <Teleport to="#modal" v-if="showModal">
    <Modal theme="sales" @close="toggleModal">
      <h1>{{ header }}</h1>
      <p>{{ content }}</p>
    </Modal>
  </Teleport>
  <button @click="toggleModal">Show modal</button>
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: { Modal },
  data() {
    return {
      title: "My first Vue App",
      header: "Prepare for the giveaway",
      content: "This is Tobe's Vue App",
      showModal: false,
    };
  },
  methods: {
    buttonClickHandler() {
      this.$refs.name.classList.add("active");
      this.$refs.name.focus();
    },
    toggleModal() {
      this.showModal = !this.showModal;
    },
  },
};
</script>

<style>
#app,
#modal {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

body {
  margin: 0;
}

h1 {
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
