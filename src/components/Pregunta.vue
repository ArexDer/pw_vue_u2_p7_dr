<template>
  <img :src="imagen" alt="No se puede ver la IMG">
    <input v-model="pregunta" type="text" placeholder="Any Question?">
    <p>Al final de la pregunta termina con una interrogación</p>
    <h1>{{ pregunta }}</h1>
    <h2>{{ respuesta }}</h2>
</template>

<script>
export default {
    data(){
        return{
            pregunta:'Hola Mundo',
            respuesta:null,
            imagen:"https://yesno.wtf/assets/yes/14-b57c6dc03aa15a4b18f53eb50d6197ee.gif"
        };
    },
    watch:{
        pregunta(value, oldValue){
            console.log(value +"VALOR");
            console.log(oldValue + "VALOR VIEJO");

            if(value.includes('?')){
                //Programamos para el llamado a la API para obtener el si o el NO.
                console.log("Aqui llamo al API")
                this.fachada();
            }

        }

    },methods:{
        async llamarAPI(){
            const data = await fetch('https://yesno.wtf/api').then((resp) =>resp.json());
           this.respuesta=data.answer;
           this.imagen=data.image;
            console.log(data);
        },
        async fachada(){
            await this.llamarAPI();
        }
    }

}
</script>

<style>

</style>