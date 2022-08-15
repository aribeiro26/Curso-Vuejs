<template>
    <div>
        <p v-if="esta_trabalhando">Estou trabalhando no momento.</p>
        <p v-else>Estou em busca de novas oportunidades.</p>
        <div>
            <button @click="showEmail">{{textoBotao}}</button>
        </div>
        <p v-show="mostrar_email"> {{email}}</p>
        <p>
            Para acessar meu portólio
            <a v-bind:href="meu_link" target="blank">Basta clicar aqui</a>
        </p>
        <Picture />
        <ul>
            <li>JavaScript</li>
            <li>PHP</li>
            <li>Python</li>
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
            textoBotao: 'Mostrar e-mail'
        };
    },
    methods:{
        showEmail(){
            this.mostrar_email = !this.mostrar_email
            if(!this.mostrar_email){
                this.textoBotao = 'Mostrar e-mail'
            }else{
                this.textoBotao = 'Esconder e-mail'
            }
        }
    }
};
</script>
