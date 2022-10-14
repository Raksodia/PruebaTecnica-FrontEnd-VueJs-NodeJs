<template>
    <tr class="fila" v-for="nota in notas" v-bind:key="nota.id">
        <td>{{ nota.id }}</td>
        <td>{{ nota.titulo }}</td>
        <td>{{ nota.fecha }}</td>
        <td><a href="#" :id="nota.id" v-on:click="actualizar();">Actualizar</a></td>
    </tr>
    
</template>

<script>
export default {
    name: 'ShowFilas',
    props: {
        notas: []
    },
    methods: {
        actualizar(){
            let idNota = event.target.id;
            this.$parent.actualizarArriba(idNota);
        }
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
