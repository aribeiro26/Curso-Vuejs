<template>
<div>
  <h1>Olá Vue!</h1>
  <p>{{name}}</p>
</div>
  
</template>

<script>
    export default{
        name: 'PrimeiroComponente',
        data(){
          return{
            name: "Alex"
          }
        }
    }
</script>