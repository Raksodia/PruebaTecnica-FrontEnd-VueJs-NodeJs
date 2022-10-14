<template>
  <div id="listNota">
    <h1 class="titulo">Listar Notas</h1>
    <ListNotas ref="listnotas" />
  </div>
</template>

<script>
import ListNotas from './ListNotas.vue'
export default {
    name: 'ListSection',
    components: {
        ListNotas
    }
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
