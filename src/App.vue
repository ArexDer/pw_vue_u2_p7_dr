<template>

  <img src="./assets/logo.png" alt="vue.logo">
 
  <!--
  <Contador encabezado="Contador Primero" v-bind:valor="1+1"/>
  <Contador encabezado="Contador Primero" :valor="1+1"/>
  <Contador encabezado="Contador Segundo" valor="5+1"/>
-->
<Contador encabezado="Hola" :valor="calcular(1,3)" :esVerdad="muestra" :valor2="667"/>
<Contador  v-bind:valor="calcular(5,5)" :esVerdad="muestra2" />
<button @:click="cambiar(1)">Cambiar Primero</button>
<button @:click="cambiar(2)">Cambiar Segundo</button>
  
</template>

<script>
import  Contador from "./components/Contador.vue"

export default {
  name: 'App',
  components: {
    Contador
  
  },
  //ESTO NO DEBERIA PROGRAMARSE EN EL APP
  methods:{
    calcular(a,b){
      return a+b;
    },
    cambiar(valor){
      if(valor===1){
        this.muestra=!this.muestra;
      }else{
        this.muestra2=!this.muestra2;
      }
      

    }
  },
  data(){
        return{
          muestra:true,
          muestra2:true
        };
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

</style>
