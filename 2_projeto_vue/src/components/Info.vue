<template>
    <div>
        <p v-if="esta_trabalhando">Estou trabalhando no momento.</p>
        <p v-else>Estou em busca de novas oportunidades.</p>
        <p v-show="mostrar_email">Utilizo as seguintes tecnologias:</p>
        <ul>
            <li>JavaScript</li>
            <li>PHP</li>
            <li>Python</li>
        </ul>
        <p>Mande uma mensagem para: {{ email }}</p>
    </div>
</template>
<script>
export default {
    name: "Info",

    data() {
        return {
            esta_trabalhando: true,
            mostrar_email: true,
            email: "alex@alex.com.br",
        };
    },
};
</script>
