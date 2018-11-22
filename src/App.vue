<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <ContactList/>
    <BlogPost 
    :title="parentTitle"
    @callParentFunction="parentFunction"
    />

  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import ContactList from './components/ContactList.vue'
import BlogPost from './components/BlogPost.vue'

export default {
  name: 'app',
  components: {
    HelloWorld,
    ContactList,
    BlogPost
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
