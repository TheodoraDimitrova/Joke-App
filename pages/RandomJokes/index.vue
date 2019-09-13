<template>
  <div class="joke">
    <h1>Enter a number and get random jokes :-) </h1>
  <form @submit.prevent="onSubmit">
    <input  type="number" min="10" max="100" step="10" v-model="count" placeholder="Enter number 10,20,30... etc" required/>
    <input type="submit" value="Render Random Jokes" />
  </form>
  <div class="joke" v-for="(joke) of arrayOfJokes" :key="joke.id">
   {{joke.value}}
  </div>
  </div>
</template>
<script>
import axios from "axios";
  
export default {
    

  title:'Take random jokes',
  data() {
    return {
      count:'',
      arrayOfJokes:[]
    }
  },
   methods: {
    
     async  onSubmit() {
      try {
        for (let i = 0; i < this.count; i++) {
          const res = await axios.get("https://api.chucknorris.io/jokes/random" );
         this.arrayOfJokes.push(res.data)
      }
      console.log(this.arrayOfJokes)
    } catch (error) {
      console.log(error);
    }
                                 
      
      this.count = "";
  
    }
  },
  
  meta:[
    {
      hid:'description',
      name:'description',
      content:"Chuck Norris Jokes"
    }
  ]

}
</script>

<style>

</style>