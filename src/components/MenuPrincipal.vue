<template>
  <div>
    <ul>
      <li><a href="#" v-on:click="home">Home</a></li>
      <li><a href="#" v-on:click="add">A&ntilde;adir Nota</a></li>
      <li><a href="#" v-on:click="list">Listar Notas</a></li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'MenuPrincipal',
  methods: {
    home(){
      window.document.getElementById("homeNota").style.display = 'block';
      window.document.getElementById("addNota").style.display = 'none';
      window.document.getElementById("listNota").style.display = 'none';
      window.document.getElementById("updateNota").style.display = 'none';
      window.document.getElementById("notas").style.display = 'none';
    },
    add(){
      window.document.getElementById("homeNota").style.display = 'none';
      window.document.getElementById("addNota").style.display = 'block';
      window.document.getElementById("listNota").style.display = 'none';
      window.document.getElementById("updateNota").style.display = 'none';
      window.document.getElementById("notas").style.display = 'none';
    },
    list(){
      window.document.getElementById("homeNota").style.display = 'none';
      window.document.getElementById("addNota").style.display = 'none';
      window.document.getElementById("listNota").style.display = 'block';
      window.document.getElementById("updateNota").style.display = 'none';
      window.document.getElementById("notas").style.display = 'block';
      this.$parent.ForcesUpdateComponent();
    },
    update(){
      window.document.getElementById("homeNota").style.display = 'none';
      window.document.getElementById("addNota").style.display = 'none';
      window.document.getElementById("listNota").style.display = 'none';
      window.document.getElementById("updateNota").style.display = 'block';
      window.document.getElementById("notas").style.display = 'none';
    }
  },
  mounted() {
      window.document.getElementById("homeNota").style.display = 'none';
      window.document.getElementById("addNota").style.display = 'none';
      window.document.getElementById("listNota").style.display = 'block';
      window.document.getElementById("updateNota").style.display = 'none';
      window.document.getElementById("notas").style.display = 'block';
  }
}
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
  overflow: hidden;
  background-color: #333;
}

li {
  float: left;
}

li a {
  display: block;
  color: white;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
}

li a:hover {
  background-color: #111;
}
</style>