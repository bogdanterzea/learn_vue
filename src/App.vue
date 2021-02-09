<template>
  <div class="form">
    <h1>{{ title }}</h1>
    <input type="text" ref="name">
    <button v-on:click="handleClick">click me</button>
    <Modal :header="header" :text="text" theme='sale'/>
  </div>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: "App",
  components: { Modal },
  data() {
    return {
      title: "My vue app",
      header: "Good job!",
      text: "Now drink some watter! :D"
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
  display: block;
  padding-bottom: 10px;
  text-align: center;
}
</style>
