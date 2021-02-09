<template>
  <div class="form">
    <h1>{{ title }}</h1>
    <input type="text" ref="name">
    <button v-on:click="handleClick">click me</button>
    <Modal />
  </div>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: "App",
  components: { Modal },
  data() {
    return {
      title: "My vue app"
    };
  },
  methods: {
    handleClick() {
      console.log(this.$refs.name)
      this.$refs.name.classList.add('active')
      this.$refs.name.focus()
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e40;
  margin-top: 60px;
}

h1 {
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
