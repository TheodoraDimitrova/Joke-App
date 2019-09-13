<template>
<div class="joke">
  <nuxt-link to="/categories"> Back to Categories</nuxt-link>
  <h2>Joke by {{$route.params.id}} category</h2>
  <hr>
  <p>
    {{joke.value}}
  </p>
  <form @submit.prevent="onSubmit">
    <input  type="number" min="10" max="100" step="10" v-model="count" placeholder="Enter number 10,20,30... etc" required/>
    <input type="submit" value="More jokes from this category" />
  </form>
   <div class="joke" v-for="(joke,index) of arrayOfJokes" :key="index">
     <p>{{joke.icon_url}}</p>
   {{joke.value}}
  </div>
  
</div>

  
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      joke: {},
      count:"",
      arrayOfJokes:[]
    };
  },
    methods: {
    
     async  onSubmit() {
      try {
        for (let i = 0; i < this.count; i++) {
          const res = await axios.get(`https://api.chucknorris.io/jokes/random?category=${this.$route.params.id}` );
         this.arrayOfJokes.push(res.data)
      }
      console.log("here")
      console.log(this.arrayOfJokes)
    } catch (error) {
      console.log(error);
    }
                                 
      
      this.count = "";
  
    }
  },
  async created() {
   try {
      const res = await axios.get(
      `https://api.chucknorris.io/jokes/random?category=${this.$route.params.id}`
    );
   this.joke=res.data;
 
     
   } catch (error) {
     console.log(error)
   }
  
  
  },

  title: "Jokes by category Id",
  meta: [
    {
      hid: "description",
      name: "description",
      content: "Chuck Norris Jokes"
    }
  ]
};
</script>
<style>
.joke{
    padding: 1rem;
    border:1px solid rgb(30, 206, 68);
    margin: 1rem;
}
</style>

