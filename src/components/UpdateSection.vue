<template>
  <div id="updateNota">
    <h1 class="titulo">Actualizar Nota</h1>
    <UpdateFormulario ref="updatef"/>
  </div>
</template>

<script>
import UpdateFormulario from './UpdateFormulario.vue'

export default {
    components: { UpdateFormulario },
    name: 'UpdateSection',
    data (){
        return { 
            arreglo : null
        }   
    },
    methods: {
        setInfo(infoUpdate){
            this.arreglo = infoUpdate;
            console.log(this.arreglo);
            this.$refs.updatef.setUpdate(this.arreglo);
        },
        loadAgainListUpdateSection(){
            this.$parent.loadAgainListNotas();
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