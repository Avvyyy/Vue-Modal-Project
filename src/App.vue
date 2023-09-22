<template>
<h1>{{ title }}</h1>
<div v-if="showModal">
  <myModal :header="header" :text="text" theme="sale" @close="toggleModal"/>
</div>
<input type="text" ref="name">
<button @click="handleClick">Click Moi</button>
<br>
<button @click="toggleModal">Show Hidden</button>
</template>

<script>
import myModal from './components/myModal'
export default {
  name: 'App',
  components: { myModal },
  data() {
    return{
      title: 'My First Vue App :)',
      header: 'Sign up for the Giveaway',
      text: 'Grab your ninja swag for half price',
      showModal: false
    }
  },
  methods:{
    handleClick() {
      console.log(this.$refs.name)
      this.$refs.name.classList.add('active')
      this.$refs.name.focus()
    },
    toggleModal() {
      this.showModal = !this.showModal
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
  color: #03cfb4;
  background: #eee;
  margin-top: 60px;
}

h1{
  border-bottom: 1px solid #ccc;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
