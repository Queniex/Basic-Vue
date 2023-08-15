<template>
  <h2>Welcome {{ first_name + " " + last_name }}!</h2>
  <button v-on:click="changeName">Change Name</button>
  <h3>My Github : <a v-bind:href="url"> Go to Link</a></h3>
  <!-- v-on could be written as @click  -->
</template>

<script>

export default {
  name: 'App',
  data(){
    return{
      first_name: "Quenie",
      last_name: "Salbiyah",
      url: "https://github.com/Queniex"
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
