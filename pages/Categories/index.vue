<template>
  <div>
    <Category v-for="(category,index) of categories" :key="index" :category="category" />
  </div>
</template>



<script>
import axios from "axios";
import Category from "../../components/Category";

export default {
  components: {
    Category
  },
  data() {
    return {
      categories: []
    };
  },
  async created() {
    try {
      const res = await axios.get(
        "https://api.chucknorris.io/jokes/categories"
      );
     
      this.categories = res.data;
    } catch (error) {
      console.log(error);
    }
  },
  head() {
    return {
      title: "Chuck Norris Jokes",
      meta: [
        {
          hid: "description",
          name: "description",
          content: "Chuck Norris Jokes"
        }
      ]
    };
  }
};
</script>

<style>
</style>