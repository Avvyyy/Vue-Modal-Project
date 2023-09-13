<template>
<h1>{{ title }}</h1>
<myModal />
<input type="text" ref="name">
<button @click="handleClick">Click Moi</button>
</template>

<script>
import myModal from './components/myModal'
export default {
  name: 'App',
  components: { myModal },
  data() {
    return{
      title: 'My First Vue App :)'
    }
  },
  methods:{
    handleClick() {
      console.log(this.$refs.name)
      this.$refs.name.classList.add('active')
      this.$refs.name.focus()
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
  color: #ff9de2;
  background: #eee;
  margin-top: 60px;
}

h1{
  border-bottom: 1px solid #ccc;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
