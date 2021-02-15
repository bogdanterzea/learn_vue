<template>
  <div class="form">
    <h1>{{ title }}</h1>
    <input type="text" ref="name">
    <button v-on:click="handleClick">click me</button>
    <div v-if="showModal">
      <Modal :header="header" :text="text" theme='sale' @close="toggleModal" >
        <h1>Big Title</h1>
        <template v-slot:links> 
          <a href="#">Sign up</a>
          <a href="#">Details</a>
        </template>
      </Modal>
    </div>
    <div v-if="showModalEat">
      <Modal :titleEat="foodTitle" :headerEat="foodHeader" @close="toggleModalEat">
        <h1>Welcome aboard!</h1>
        <template v-slot:links>
          <h2>Grab a sandwitch</h2>
          <a href="https://www.subway.com/en-us">FOOD HERE!</a>
          <a href="https://www.bk.com/">FOOD HERE2!</a>
        </template>
      </Modal>
    </div>
    <br>
    <br>
    <button @click="toggleModal">Modal toggle :D</button>
    <button @click="toggleModalEat">FOOD HERE FAT MAN!</button>
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
      text: "Now drink some watter! :D",
      foodTitle: "Grab a sandwitch",
      foodHeader: "Don't forget the ketchup!!",
      showModal: false,
      showModalEat: false,
    };
  },
  methods: {
    handleClick() {
      console.log(this.$refs.name)
      this.$refs.name.classList.add('active')
      this.$refs.name.focus()
    },
    toggleModal() {
      this.showModal = !this.showModal
    },
    toggleModalEat() {
      this.showModalEat = !this.showModalEat
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
