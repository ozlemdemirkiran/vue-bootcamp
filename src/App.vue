<template>
  <div id="app">
   <nav class="navbar navbar-expand navbar-dark bg-dark">
     <router-link to="/" class="navbar-brand">TechCareer</router-link>
     <div class="navbar-nav mr-auto">
       <li class="nav-item">
         <router-link to="/tutorials" class="nav-link">Tutorials List </router-link>
       </li>
       <li class="nav-item">
         <router-link to="/ekle" class="nav-link">Tutorial Ekle </router-link>
       </li>
     </div>
   </nav>
   <div class="container mt-5">
      <router-view/>
   </div>
  </div>
  
  <!-- https://jsonplaceholder.typicode.com/todos Bu sitedekileri consola çek ödev!! -->
  <!-- https://codeshare.io/vuebootcamp  kod paylaşımı -->
</template>

<script>
export default {
    name : "app"
}
</script>