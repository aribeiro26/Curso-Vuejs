<template>
    <section
        class="is-flex is-align-items-center is-justify-content-space-between"
    >
        <Cronometro :tempoEmSegundos="tempoEmSegundos" />
        <Botao
            @clicado="Iniciar"
            icone="fas fa-play"
            texto="play"
            :desabilitado="cronometroRodando"
        />
        <Botao
            @clicado="Finalizar"
            icone="fas fa-stop"
            texto="stop"
            :desabilitado="!cronometroRodando"
        />
    </section>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Cronometro from "./Cronometro.vue";
import Botao from "./Botao.vue";

export default defineComponent({
    name: "TemporizadorTraked",
    emits: ["aoTemporizadorFinalizado"],
    components: {
        Cronometro,Botao
    },
    data() {
        return {
            tempoEmSegundos: 0,
            cronometro: 0,
            cronometroRodando: false,
        };
    },

    methods: {
        // começar a contagem
        // 1 seg = 1000ms
        Iniciar() {
            this.cronometroRodando = true;
            this.cronometro = setInterval(() => {
                this.tempoEmSegundos += 1;
            }, 1000);
        },
        Finalizar() {
            this.cronometroRodando = false;
            clearInterval(this.cronometro);
            this.$emit("aoTemporizadorFinalizado", this.tempoEmSegundos); // evento e payload
            this.tempoEmSegundos = 0;
        },
    },
});
</script>
