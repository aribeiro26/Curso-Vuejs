<template>
    <div>
        <button @click="ativar">Clique aqui!</button>
        <span v-show="ativou">Ativado!</span>
    </div>
</template>
<script>
export default {
    name: "Reutilizacao",
    data() {
        return {
            ativou: false,
        };
    },
    components: {},
    methods: {
        ativar() {
            this.ativou = !this.ativou; // executa o estado ao contrario do que está
        },
    },
};
</script>
