<template>
  <div id="app">
    <div id="nav">
      <top-header></top-header>
      <!-- <router-link to="/">Home</router-link> |
      <router-link :to="{ name: 'About' }">About Us</router-link> | 
      <router-link :to="{ name: 'Contact' }">Contact</router-link> -->
    </div>
    <router-view/>
  </div>
</template>


<script>
import TopHeader from '@/components/TopHeader.vue';
 export default {
   components: {
     "top-header": TopHeader
   }
 };
</script>


<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.modal {
  display: block;
  position: relative;
  height: auto;
}
#nav {
  padding: 0px 0px 30px 0px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
img {
  width: 100%;
}
</style>
