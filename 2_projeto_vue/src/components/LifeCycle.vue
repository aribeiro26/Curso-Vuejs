<template>
    <div>
        <h1>
            Meu Nome é: {{nome}}
        </h1>
    </div>
</template>
<script>
export default{
    name: 'LifeCycle',
    data(){
        return{
            nome: 'Ainda não sei'
        }
    },
    created(){
        setTimeout(()=>{
            this.nome = "Alex"
        }, 1000)
        
    },
    mounted(){
          setTimeout(()=>{
            this.nome = "Ribeiro"
        }, 2000)
        
       
    }
}
</script>