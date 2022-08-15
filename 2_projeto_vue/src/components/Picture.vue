<template>
    <img :src="avatar" :alt="descricao">
</template>
<script>
export default{
    data(){
        return{
            avatar: "img/avatar.png",
            descricao: "Alex Ribeiro"
        }
    }
}
</script>