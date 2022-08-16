<template>
<div>
  <h1>Olá Vue!</h1>
  <p>{{name}}</p>
  <MultiplosEventos/>
  <Reutilizacao/>
</div>
  
</template>

<script>
import MultiplosEventos from "@/components/MultiplosEventos.vue"
import Reutilizacao from "@/components/Reutilizacao.vue"
    export default{
        name: 'PrimeiroComponente',
        data(){
          return{
            name: "Alex"
          }
        },
        components:{
          MultiplosEventos,
          Reutilizacao
        }
    }
</script>