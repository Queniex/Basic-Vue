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

    <div class="container-2-item">
      <h3>Loop Condition : </h3>
      <div v-if="clothes.length">
        <ul v-for="item in clothes" :key="item.id">
        {{ item.id }} || {{ item.title }}
        </ul>
      </div>
      <div v-else>
        <h1>No Data Found</h1>
      </div> 
    </div>
  </div> 

  <hr>

  <div class="container-3">
    <div class="container-2-item">
      <h3>Loop Using "Hook LifeCycle" : </h3>
      <div v-if="items.length">
        <ul v-for="item in items" :key="item.id">
        {{ item.id }} → {{ item.title }}
        </ul>
      </div>
      <div v-else>
        <h1>No Data Found</h1>
      </div> 
    </div>

    <div class="container-2-item">
      <h3>Search using Computed Properties : </h3>
      <input type="text" v-model="search" placeholder="Enter Keyword..">
    </div>

    <div class="container-2-item">
      <h3>List of Items : </h3>
      <ul v-for="item in searchData" :key="item.id">
        {{ item.id }} || {{ item.title }}
      </ul>
    </div>

  </div> 

  <hr>

  <div class="container-4">
    <h2>Welcome {{ first_name + " " + last_name }}!</h2>
    <button v-on:click="changeName">Change Name</button>
      <!-- The v-on directive can also be represented as @click -->
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
      search: "",
      products: [
        {id: 1, title: "A"},
        {id: 2, title: "B"},
        {id: 3, title: "C"},
        {id: 4, title: "D"},
        {id: 5, title: "E"}
      ],
      clothes: [],
      items : []
    };
  },
  beforeMount(){
    console.log("Before Mount");
  },
  mounted(){
    console.log("Mounted");
  },
  beforeCreate(){
    console.log("Before Create");
  },
  created(){
    this.items = [
      {id: 1, title: "AAAA"},
      {id: 2, title: "BBBB"},
      {id: 3, title: "CCCC"},
      {id: 4, title: "DDDD"},
      {id: 5, title: "EEEE"}
    ]
  },
  computed: {
    searchData(){
      return this.items.filter((item) => {
        return item.id.toString().match(this.search);
      });
    }
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
  grid-template-columns: auto auto auto;
}

.container-3{
  /* border: 1px red solid; */
  display: grid;
  grid-template-columns: auto auto auto;
}

.container-2-item{
  height: 15rem;
  width: 22rem;
  margin-left: 3rem;
  margin-right: 3rem;
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
