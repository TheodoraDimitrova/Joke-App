<template>
  <header class="header">
    <h1 class="title">Chuck Norris Jokes</h1>
    <ul>
      <li>
        <nuxt-link to="/">Home</nuxt-link>
        <nuxt-link to="/randomJokes">Random Jokes</nuxt-link>
        <nuxt-link to="/categories">Categories</nuxt-link>
      </li>
    </ul>
  </header>
</template>
<script>
export default {
  name: "AppHeader"
};
</script>

<style>
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 1rem;
  padding-bottom: 1rem;
  border-bottom: 1rem;
  border-bottom: 1px dotted #cccccc;
}
.header .title {
  font-size: 3rem;
  color: blueviolet;
  padding: 1rem;
}

.header ul {
  display: flex;
}
.header a {
  display: inline-block;
  background: #333;
  color: #fff;
  padding: 0.3 rem 1rem;
  margin-right: 0.5rem;
}
</style>