<template>
<div>
  <h1>Prueba Tecnica - FrontEnd</h1>
  <MenuPrincipal />
  <HomeSection />
  <AddSection  />
  <ListSection />
  <UpdateSection />
</div>
</template>

<script>
import MenuPrincipal from './components/MenuPrincipal.vue'
import HomeSection from './components/HomeSection.vue'
import AddSection from './components/AddSection.vue'
import ListSection from './components/ListSection.vue'


export default {
  name: 'App',
  components: {
    MenuPrincipal,
    HomeSection,
    AddSection,
    ListSection,
    
  },
  methods: {
    ForcesUpdateComponent() {
      // your code
      this.$forceUpdate();
      // your code
    }
  },
  data (){
  return { 
      
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
