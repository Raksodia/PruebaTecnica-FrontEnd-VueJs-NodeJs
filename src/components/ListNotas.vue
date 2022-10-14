<template>
    <div>
       <div id="notas"> 
            <table id="lista">
                <thead>
                    <tr>
                        <th>##</th>
                        <th>Titulo</th>
                        <th>Fecha</th>
                        <th>Actualizar</th>
                    </tr>
                </thead>
                <tbody>
                    <ShowFilas v-bind:notas="notas" />
                </tbody>
            </table>
        </div>
        <UpdateSection ref="update"/>
    </div>
</template>

<script>
import axios from 'axios';
import ShowFilas from './ShowFilas.vue'
import UpdateSection from './UpdateSection.vue'
export default {
    name: 'ListNotas',
    components: {
        ShowFilas,
        UpdateSection
    },
    data (){
        return { 
            notas : null,
            info: null
        }   
    },
    methods: {
        actualizarArriba(id){
            window.document.getElementById("notas").style.display = 'none';
            window.document.getElementById("updateNota").style.display = 'block';

            let serviceUri = 'http://localhost:3050/notas/'+id;
       
            axios.get(serviceUri)
            .then( response => {
                this.info = response.data;
                this.$refs.update.setInfo(this.info);
            })
            .catch(error => {
                console.log(error);
                return;
            });
        },
        loadAgainListNotas(){
            console.log("cargando");
            let serviceUri = 'http://localhost:3050/notas';
       
            axios.get(serviceUri)
            .then( response => {
                this.notas = response.data;
                window.document.getElementById("homeNota").style.display = 'none';
                window.document.getElementById("addNota").style.display = 'none';
                window.document.getElementById("listNota").style.display = 'block';
                window.document.getElementById("updateNota").style.display = 'none';
                window.document.getElementById("notas").style.display = 'block';
            })
            .catch(error => {
                console.log(error);
                return;
            });
        }
    },
    mounted() {
        let serviceUri = 'http://localhost:3050/notas';
       
        axios.get(serviceUri)
        .then( response => {
            this.notas = response.data;
        })
        .catch(error => {
            console.log(error);
            return;
        });
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
.titulo {
  margin: 0;
  text-align: left;
  padding: 30px 20px 30px 10px;
}

#lista {
  font-family: Arial, Helvetica, sans-serif;
  border-collapse: collapse;
  width: 60%;
}

#lista td, #lista th {
  border: 1px solid #ddd;
  padding: 8px;
}

#lista tr:nth-child(even){background-color: #f2f2f2;}

#lista tr:hover {background-color: #ddd;}

#lista th {
  padding-top: 12px;
  padding-bottom: 12px;
  text-align: center;
  background-color: #333;
  color: white;
}
</style>
