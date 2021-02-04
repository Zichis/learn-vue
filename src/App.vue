<template>
  <Navbar v-bind:company="company" />
  <div class="p-5">
    <div class="p-2">
      <input class="w-full border-b border-gray-300 focus:border-green-400 py-1 focus:outline-none" type="text" name="" id="" placeholder="Search..." v-on:keyup="searchMeal" v-model="searchWord">
    </div>
    <div class="p-2" v-if="meals.length === 0">
      <h3>No meal found...</h3>
    </div>
    <div class="flex flex-wrap">
      <div class="p-2 w-full sm:w-1/2 md:w-1/3" v-bind:key="meal.id" v-for="meal in meals">
        <div class="rounded overflow-hidden border shadow">
          <div :style='{height: "200px", background: `url(${meal.urlImage})`, "background-position": "center", "background-size": "cover"}'></div>
          <div class="p-2">
            <h3 class="font-bold text-gray-700">{{ meal.name }}</h3>
            <h4 class="text-xl text-yellow-500 font-extralight">{{ meal.price }}</h4>
            <button class="px-1 bg-green-500 text-white mr-2 rounded hover:bg-green-700">Buy</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import Navbar from './components/Navbar'

export default {
  name: 'App',
  components: {
    Navbar
  },
  data () {
    return {
      company: "Unique Taste",
      meals: [
        {
          name: "Spaghetti",
          price: 2500.00,
          urlImage: "https://images.pexels.com/photos/2347311/pexels-photo-2347311.jpeg?auto=compress&cs=tinysrgb&dpr=2&w=500"
        },
        {
          name: "Rice & Chicken",
          price: 2500.00,
          urlImage: "https://images.pexels.com/photos/1624487/pexels-photo-1624487.jpeg?auto=compress&cs=tinysrgb&dpr=2&w=500"
        },
        {
          name: "Spring Rolls",
          price: 1200.00,
          urlImage: "https://images.pexels.com/photos/4001867/pexels-photo-4001867.jpeg?auto=compress&cs=tinysrgb&dpr=2&w=500"
        },
        {
          name: "Samosa",
          price: 1500.00,
          urlImage: "https://images.pexels.com/photos/4449068/pexels-photo-4449068.jpeg?auto=compress&cs=tinysrgb&dpr=2&w=500"
        },
        {
          name: "Cake",
          price: 1500.00,
          urlImage: "https://images.pexels.com/photos/1854652/pexels-photo-1854652.jpeg?auto=compress&cs=tinysrgb&dpr=2&w=500"
        },
        {
          name: "Smoothie",
          price: 800.00,
          urlImage: "https://images.pexels.com/photos/775030/pexels-photo-775030.jpeg?auto=compress&cs=tinysrgb&dpr=2&w=500"
        }
      ],
      searchWord: "",
      tempMeals: [
        {
          name: "Spaghetti",
          price: 2500.00,
          urlImage: "https://images.pexels.com/photos/2347311/pexels-photo-2347311.jpeg?auto=compress&cs=tinysrgb&dpr=2&w=500"
        },
        {
          name: "Rice & Chicken",
          price: 2500.00,
          urlImage: "https://images.pexels.com/photos/1624487/pexels-photo-1624487.jpeg?auto=compress&cs=tinysrgb&dpr=2&w=500"
        },
        {
          name: "Spring Rolls",
          price: 1200.00,
          urlImage: "https://images.pexels.com/photos/4001867/pexels-photo-4001867.jpeg?auto=compress&cs=tinysrgb&dpr=2&w=500"
        },
        {
          name: "Samosa",
          price: 1500.00,
          urlImage: "https://images.pexels.com/photos/4449068/pexels-photo-4449068.jpeg?auto=compress&cs=tinysrgb&dpr=2&w=500"
        },
        {
          name: "Cake",
          price: 1500.00,
          urlImage: "https://images.pexels.com/photos/1854652/pexels-photo-1854652.jpeg?auto=compress&cs=tinysrgb&dpr=2&w=500"
        },
        {
          name: "Smoothie",
          price: 800.00,
          urlImage: "https://images.pexels.com/photos/775030/pexels-photo-775030.jpeg?auto=compress&cs=tinysrgb&dpr=2&w=500"
        }
      ]
    }
  },
  methods: {
    searchMeal: function(){
      this.meals = this.tempMeals.filter((meal) => meal.name.toLowerCase().search(this.searchWord.toLowerCase()) > -1);
      if (this.searchWord === "") {
        this.meals = this.tempMeals;
      }
    }
  }
}
</script>

<style>
#app {
  font-family: 'Raleway', sans-serif;
}
#companyName {
  font-family: 'Kurale', serif;
}
</style>
