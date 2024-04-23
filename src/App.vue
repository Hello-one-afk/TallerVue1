<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/>

<div>
  <label for="">Nombre de la lista </label>
  <input id="nombre-lista" v-model="nombreLista" @keyup.enter="agregarNombreLista()">
  <h1>Lista llamada {{ nombreLista }}</h1>
  <div>
  
  <button id="btn"> Agregar Tarea </button> 

  <button id="btn"> Modificar Tarea </button> 
  <button id="btn"> Quitar Tarea </button> 
  </div>


  <label for="">Agregar tarea</label>
  <input v-model="nuevaTarea" @keyup.enter="agregarTarea()">
  <ul>
    Tareas
    <li v-for="(tarea,index) in tareas" :key="index">
       {{"Tarea numero "+index+" | " + tarea }}
    </li>
  </ul>

  <label for="">Numero de la tarea a eliminar</label>
  <input v-model = "numeroTarea" @keyup.enter="quitarTareas()">
</div>


</template>

<script>
/*
Agregar tarea: Poder agregar alguna tarea a la lista de quehaceres. (20 puntos)
● Quitar tareas: Poder eliminar una tarea de la lista de quehaceres. (20 puntos)
● Modificar tareas: Poder modificar una tarea de la lista de quehaceres. (10 puntos
*/

import { ref } from "vue";
export default {
  name: 'App',
  data(){
    return{
      nombreLista: ref(''),
      nombreTarea: ref(''),
      tareas: ref([]),
      nuevaTarea: ref(''),
      numeroTarea: ref('')



    };
  },
  methods:{
    agregarNombreLista(){
      console.log(`Nombre de la lista: ${this.nombreLista}`);
    },

    agregarTarea(){
      this.tareas.push(this.nuevaTarea);
      this.nuevaTarea = '';
      console.log(this.nuevaTarea);
      
    },
    quitarTareas(){
      

    }

  },
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
#btn{
  margin-top: 5%;
  margin-right: 2%;
}
</style>
