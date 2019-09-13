<template>
  <div class="search">
    <h2>Welcome To Chuck Norris Jokes App</h2>
    <SearchJokes v-on:search-text="searchText" />
    <div class="joke" v-for="(joke,index) of searchedJokes" :key="index" >
   {{joke.value}}
    </div>
  </div>
</template>

<script>
import SearchJokes from "../components/SearchJokes";
import axios from "axios";
export default {
   data() {
    return {
      searchedJokes: []
    };
  },
  components: {
    SearchJokes
  },
 
  methods: {
    async searchText(text) {
      try {
        const res = await axios.get(
          `https://api.chucknorris.io/jokes/search?query=${text}`
        );
        // this.jokes=res.data.result
        this.searchedJokes=res.data.result
        console.log(this.searchedJokes)
      } catch (error) {
        console.log(error);
      }
    }
  },
  title: "Welcome To Chuck Norris Jokes",
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
.search {
  padding: 1rem;
  margin: 1rem
}
</style>

