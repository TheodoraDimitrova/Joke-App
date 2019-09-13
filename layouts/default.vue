<template>
  <div class="container">
    <AppHeader />
    <nuxt />
  </div>
</template>


<script>
import AppHeader from "../components/AppHeader";
export default {
  components: {
    AppHeader
  }
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: Arial, Helvetica, sans-serif;
  font-size: 1rem;
  line-height: 1.6;
  background: #ccc;
}

a {
  color: #666;
  text-decoration: none;
}
ul {
  list-style: none;
}

.container {
  max-width: 800px;
  margin: 2rem auto;
  overflow: hidden;
  padding: 1rem 2 rem;
  background: #ffffff;
}
a:hover {
  color: #dc134d;
}


.joke {
    padding: 1rem;
    border:1px solid rgb(174, 73, 221);
    margin: 1rem;

}

</style>

