<template>
    <StyleMultiplos>
        <!-- <button @click="primeiro($event), segundo($event)">
            Ativar Multiplos Eventos
        </button> -->
        <button @click="primeiro($event), segundo($event)">
            Ativar Multiplos Eventos
        </button>
        <p>{{ multiplos_eventos }}</p>
    </StyleMultiplos>
</template>
<script>
import StyleMultiplos from "@/components/Styles/MultiplosEventos.styles";
export default {
    name: "MultiplosEventos",
    data() {
        return { multiplos_eventos: "" };
    },
    components: {
        StyleMultiplos,
    },
    methods: {
        primeiro(e) {
            this.multiplos_eventos = "Primeiro evento ativado!";
        },
        segundo(e) {
            setTimeout(
                () => (this.multiplos_eventos = "Segundo evento ativado!"),
                500
            );
        },
    },
};
</script>
