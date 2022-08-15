<template>
    <div>
        <h1>Meu Nome é: {{ nome }}</h1>
    </div>
</template>
<script>
export default {
    name: "LifeCycle",
    data() {
        return {
            nome: "Ainda não sei",
        };
    },
    created() {
        setTimeout(() => {
            this.nome = "Alex";
        }, 1000);

        this.lifeCycle();
    },
    mounted() {
        setTimeout(() => {
            this.nome = "Ribeiro";
        }, 2000);
        this.lifeCycle();
    },
    methods: {
        lifeCycle() {
            console.log("Executou");
        },
    },
};
</script>
