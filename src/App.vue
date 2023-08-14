<template>
  <h2>Welcome {{ first_name + " " + last_name }}!</h2>
  <button v-on:click="changeName">Change Name</button>
  <!-- v-on could be written as @click  -->
</template>

<script>

export default {
  name: 'App',
  data(){
    return{
      first_name: "Quenie",
      last_name: "Salbiyah"
    };
  },
  methods:{
    changeName(){
      this.first_name = "Lailany";
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
  color: #2c3e50;
  margin-top: 60px;
}
</style>
