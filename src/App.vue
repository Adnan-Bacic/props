<template>
  <div id="app">
    <Navbar v-bind:name="name" v-bind:number="number"/>
    <Food v-bind:food="food" @delete="removeFood"/>
  </div>
</template>

<script>
import Navbar from './Navbar.vue'
import Food from './Food.vue'

export default {
  name: 'app',

  components:{
    Navbar: Navbar,
    Food: Food
  },

  data () {
    return {
      name: 'adnan bacic',
      number: '123',

      food:[
        { name: 'Rye bread', veggie: true, vegan: true },
        { name: 'Eggs', veggie: true, vegan: false },
        { name: 'Pasta', veggie: true, vegan: false },
        { name: 'Chips', veggie: true, vegan: true },
      ]
    }
  },

  methods:{
    removeFood(payload){
      console.log(payload)
      this.food = this.food.filter(food =>{
        return food.name !== payload.name;
      })
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
