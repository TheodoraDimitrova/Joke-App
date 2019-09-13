<template>
<div class="joke">
  <nuxt-link to="/categories"> Back to Categories</nuxt-link>
  <h2>Joke by {{$route.params.id}} category</h2>
  <hr>
  <p>
    {{joke.value}}
  </p>
  <nuxt-link to="/more">More</nuxt-link>
</div>

  
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      joke: {}
    };
  },
  async created() {
   try {
      const res = await axios.get(
      `https://api.chucknorris.io/jokes/random?category=${this.$route.params.id}`
    );
   this.joke=res.data;
   console.log(this.joke)
     
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

