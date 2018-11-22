<template>
  
        <nav class="navbar navbar-light bg-dark">
  <a class="navbar-brand" href="#">Our firs navbar</a>
  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNavAltMarkup" aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">
    <span class="navbar-toggler-icon"></span>
  </button>
  <div class="collapse navbar-collapse" id="navbarNavAltMarkup">
    <div class="navbar-nav">
     
      <router-link class="nav-link" to="contacts">Contacts</router-link>
     
      <router-link class="nav-link" to="add-contacts">Add Contacts</router-link>
    </div>
  </div>
</nav>
</template>

<script>
export default {};
</script>
<style scoped>
 .navbar-brand {
     color: white;
 }
</style>


