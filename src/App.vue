<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <NavBar/>
    <!-- <ContactList/> -->
    <!-- <BlogPost 
    :title="parentTitle"
    @callParentFunction="parentFunction"
    /> -->
    

  <router-view></router-view>

  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import ContactList from './components/ContactList.vue'
import BlogPost from './components/BlogPost.vue'
import NavBar from './components/NavBar.vue'
import ContactDetails from './components/ContactDetails.vue'

export default {
  name: 'app',
  components: {
    HelloWorld,
    ContactList,
    BlogPost,
    NavBar,
    ContactDetails
  },
  data() {
    return {
      parentTitle: 'Blog title'
    };
  },
  methods: {
    parentFunction(name, age) {
      console.log('Hi from parent' + name + ' ' + age);
      
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
