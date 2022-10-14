<template>
  <div id="addNota">
    <h1 class="titulo">A&ntilde;adir Nota</h1>
    <AddFormulario />
  </div>
</template>

<script>
import AddFormulario from './AddFormulario.vue'

export default {
  components: { AddFormulario },
  name: 'AddSection'
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.titulo {
  margin: 0;
  text-align: left;
  padding: 30px 20px 30px 10px;
}

</style>
