<template>
  <Header />
  <Info @click="openModal" />
  <About />
  <Modal :openModal="active" />
</template>

<script>
import Header from "./components/Header.vue";
import Info from "./components/Info.vue";
import About from "./components/About.vue";
import Modal from "./components/Modal.vue";
export default {
  data() {
    return {
      active: false,
    }
  },

  components: {
    Header, Info,
    About, Modal,
  },

  methods: {
    openModal() {
      this.active = !this.active;
    },
  }
}
</script>