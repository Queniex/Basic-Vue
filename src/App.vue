<template>

  <div class="container-1">
    <h2>Welcome {{ first_name + " " + last_name }}!</h2>
    <button v-on:click="changeName">Change Name</button>
      <!-- The v-on directive can also be represented as @click -->
  </div>

  <hr>

  <div class="container-2">
    <div class="container-2-item">
      <h3>My Github : <a v-bind:href="url"> Go to Link</a></h3>
      <input type="text" v-model="name">
      <h1>{{ name }}</h1>
    </div>
    
    <div class="container-2-item">
      <h3>Loop Condition : </h3>
      <div v-if="products.length">
        <ul v-for="item in products" :key="item.id">
        {{ item.id }} || {{ item.title }}
        </ul>
      </div>
      <div v-else>
        <h1>No Data Found</h1>
      </div> 
    </div>
  </div>

  <div class="day-3">
    <hr>
  </div>

</template>

<script>
export default {
  name: 'App',
  data(){
    return{
      first_name: "Quenie",
      last_name: "Salbiyah",
      url: "https://github.com/Queniex",
      name: "",
      products: [
        {id: 1, title: "A"},
        {id: 2, title: "B"},
        {id: 3, title: "C"},
        {id: 4, title: "D"},
        {id: 5, title: "E"}
      ]
    };
  },
  methods:{
    changeName(){
      this.first_name = "Back";
    }
  }
}
</script>

<style>
.container-1{
  text-align: center;
  margin-bottom: 30px;
}

.container-2{
  /* border: 1px red solid; */
  display: grid;
  grid-template-columns: auto auto;
}

.container-2-item{
  margin-left: 2rem;
  margin-right: 2rem;
  /* border: 1px red solid; */
  text-align: center;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 30px;
}
</style>
