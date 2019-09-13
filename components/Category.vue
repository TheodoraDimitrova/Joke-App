<template>
<nuxt-link :to="'categories/'+category">
  <div class='category'>
    <h3>{{category}}</h3>

  </div>
</nuxt-link>



  
</template>
<script>

export default {
  name:'Category',
  props:['category']

}
</script>

<style>
.category {
    padding: 1rem;
    border:1px dotted #3d1ab9;
    margin: 1rem;

}
.category:hover{
  background-color: blueviolet;
  color:#000;
}
</style>