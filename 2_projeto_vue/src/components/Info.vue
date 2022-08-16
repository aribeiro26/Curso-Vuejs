<template>
    <div>
        <p v-if="esta_trabalhando">Estou trabalhando no momento.</p>
        <p v-else>Estou em busca de novas oportunidades.</p>
        <div>
            <button @click="showEmail">{{ textoBotao }}</button>
        </div>
        <p v-show="mostrar_email">{{ email }}</p>
        <p>
            Para acessar meu portólio
            <a v-bind:href="meu_link" target="blank">Basta clicar aqui</a>
        </p>
        <Picture />
        <p>Utilizo as seguintes tecnologias para back-end:</p>
        <ul>
            <li
                v-for="(techonoly, index) in backend_tecnologies"
                v-bind:key="index"
            >
                {{ techonoly }}
            </li>
        </ul>
        <p>Utilizo as seguintes tecnologias para front-end:</p>
        <ul>
            <li v-for="techonoly in frontend_tecnologies" :key="techonoly.id">
                {{ techonoly.language }}
            </li>
        </ul>
        <p>Mande uma mensagem para: {{ email }}</p>
    </div>
</template>
<script>
import Picture from "./Picture.vue";
export default {
    name: "Info",
    components: { Picture },
    data() {
        return {
            esta_trabalhando: false,
            mostrar_email: true,
            email: "alex@alex.com.br",
            meu_link: "https://google.com.br",
            textoBotao: "Mostrar e-mail",
            backend_tecnologies: ["JavaScript", "PHP", "Python"],
            frontend_tecnologies: [
                { id: 1, language: "HTML" },
                { id: 2, language: "CSS" },
                { id: 3, language: "VUE" },
            ],
        };
    },
    methods: {
        showEmail() {
            this.mostrar_email = !this.mostrar_email;
            if (!this.mostrar_email) {
                this.textoBotao = "Mostrar e-mail";
            } else {
                this.textoBotao = "Esconder e-mail";
            }
        },
    },
};
</script>
