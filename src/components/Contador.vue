<template>

<h2>{{titulo}}</h2>
<!--metods
<p>{{numero}} <sup>2</sup>={{ calcularCuadrado() }}</p>
<p>{{numero}} <sup>2</sup>={{ calcularCuadrado() }}</p>
<p>{{numero}} <sup>2</sup>={{ calcularCuadrado() }}</p>
<p>{{numero}} <sup>2</sup>={{ calcularCuadrado() }}</p>
<p>{{numero}} <sup>2</sup>={{ calcularCuadrado() }}</p>
-->

<!--Propieda Computada-->
<div class="prop-Com">


<p>{{numero}} <sup>2</sup>={{ calcularCuadradoComputado }}</p>
<p>{{numero}} <sup>2</sup>={{ calcularCuadradoComputado }}</p>
<p>{{numero}} <sup>2</sup>={{ calcularCuadradoComputado }}</p>
<p>{{numero}} <sup>2</sup>={{ calcularCuadradoComputado }}</p>
<p>{{numero}} <sup>2</sup>={{ calcularCuadradoComputado }}</p>
</div>
<div class="botones">
    <button class="mas" v-on:click="incremetar()">+ 1</button>
    <button class="menos"  v-on:click="decremetar()">- 1</button>
</div>




</template>

<script>
export default {
 
    data(){
        return{
            numero : 15,
            titulo:'Contador'
        }
    },
    methods:{
        calcularCuadrado(){
            console.log("Ingreso al método creado")
        return this.numero*this.numero;
        },
        incremetar(){
            this.numero++;
        },
        decremetar(){
            this.numero--;
        }

    },
    computed:{
        calcularCuadradoComputado(){
            console.log("Ingreso al  Computado")
        return this.numero*this.numero;

        }
    }
    

}
</script>

<style scoped>



button{
    background: wheat;
    padding: 10px 40px;
    margin-right: 12px; 
    border-radius: 5px;
    border: 1px solid black;
    cursor: pointer;
   
}
.mas{
    background: #a7c957;

}
.menos{
    background: #bc4749;

}
button:hover{
    background: #778da9;
}


</style>
