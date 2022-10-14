<template>
  <div class="formulario" >
    <div id="messageupdate" class="message" v-html="mensaje"></div>
    <form>
        <label for="titulo" class="label">Titulo</label>
        <input type="text" id="titulo" name="titulo" v-model="titulo">
        <label for="cuerpo" class="label">Nota</label>
        <textarea id="cuerpo" name="cuerpo" v-model="cuerpo"></textarea>
        <input type="button" value="Guardar" v-on:click="actualizar">
    </form>
  </div>
</template>

<script>
import axios from 'axios';
export default {
    name: 'UpdateFormulario',
    data (){
        return { 
            id: null,
            titulo: "",
            cuerpo: "",
            mensaje: ""
        }   
    },
    methods:{
        
        
        actualizar(){
            let request = {
                titulo: this.titulo,
                cuerpo: this.cuerpo
            };
            let serviceUri = 'http://localhost:3050';
       
            axios.post(serviceUri + "/update/" + this.id,request).then(response => {
                console.log(response.data);
                if(response.status == 200 )
                {
                    this.mensaje = "Su Nota ha sido Actualizada";
                    this.mensaje ="";
                    this.$parent.loadAgainListUpdateSection();
                }
            });
            
        },
        setUpdate(obj){
            this.id = obj[0].id;
            this.titulo = obj[0].titulo;
            this.cuerpo = obj[0].cuerpo;
        }
    },
    mounted() {
        
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

.label {
    color:#555;
    font-weight: 700;
    font-size: 20px;
    text-align: left;
    padding: 15px 10px;
}

.formulario {
    width: 60%;
    padding: 30px;
    text-align: left;
    border-radius: 5px;
    background-color: #f2f2f2;
}

input[type=text] {
    width: 100%;
    font-size: 16px;
    padding: 10px;
    margin: 8px 0;
    box-sizing: border-box;
    border: 3px solid #ccc;
    border-radius: 4px;
    -webkit-transition: 0.5s;
    transition: 0.5s;
    outline: none;
}

input[type=text]:focus {
    border: 3px solid #555;
}

textarea {
    width: 100%;
    height: 150px;
    padding: 10px;
    box-sizing: border-box;
    border: 3px solid #ccc;
    border-radius: 4px;
    font-size: 16px;
    resize: none;
    transition: 0.5s;
    outline: none;
}

textarea:focus {
    border: 3px solid #555;
}

input[type=submit] {
    width: 100%;
    background-color: #333;
    color: white;
    padding: 14px 20px;
    margin: 8px 0;
    border: none;
    border-radius: 4px;
    cursor: pointer;
}

input[type=submit]:hover {
    background-color: #625555;
}

.message {
    color: red;
    font-size: 16px;
    font-weight: 600;
    height: 16px;
    text-align: right;
}
</style>