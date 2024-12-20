<template>

<!--metods
<h2>{{titulo}}</h2>
<p>{{numero}} <sup>2</sup>={{ calcularCuadrado() }}</p>
<p>{{numero}} <sup>2</sup>={{ calcularCuadrado() }}</p>
<p>{{numero}} <sup>2</sup>={{ calcularCuadrado() }}</p>
<p>{{numero}} <sup>2</sup>={{ calcularCuadrado() }}</p>
<p>{{numero}} <sup>2</sup>={{ calcularCuadrado() }}</p>
-->

<!--Propieda Computada-->
<div class="prop-Com">

<h2>{{encabezado}} : {{valor2}}</h2>
<p>{{numero}} <sup>2</sup>={{ calcularCuadradoComputado }}</p>
<p>{{numero}} <sup>2</sup>={{ calcularCuadradoComputado }}</p>

</div>
<div class="botones">
    <button class="mas" v-on:click="incremetar()">+ 1</button>
    <button class="menos"  v-on:click="decremetar()">- 1</button>
</div>

<div v-if="esVerdad">
    <h2 style="background: wheat;">FELIZ NAVIDAD</h2>
</div>




</template>

<script>
export default {
 
    data(){
        return{
            numero : this.valor,
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
    },

    //Otra forma de declarar el propr y yo puedo especificar el tipo de dato.
    props:{
    encabezado:{
        type:String,
        required:false,
        default:"Texto",
        validator(value){
           if(!value.includes==='h'){
            return value;
           }
        }
    },
    valor: Number,
    valor2:{
        type:Number,
        required:false,
        default:666,
        validator(value){
            //programo mi validacion bajo mi criterio y retorno TRUE cuando cumple
            // Y retorno FALSE cuando no cumple para mi.
            return value<=666;
        }

    },
    esVerdad:{
        type: Boolean,
        required:true
    },
    arreglo:Array,
    fecha:Date,
    persona:Object     
}
    

   // props:['encabezado','valor']
    

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
    font-size: 16px;
   
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
