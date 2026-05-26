<script setup>
import ButtonChild from './ButtonChild.vue';
    defineProps(['id', 'descricao', 'status'])
    defineEmits(['editar', 'excluir'])
</script>

<template>
    <li>
        <span :class="{concluida: status === 'concluida'}">
        {{ descricao }}
        </span>
        <ButtonChild @clique="$emit('editar', id)">Editar</ButtonChild>
        <ButtonChild @clique="$emit('excluir', id)">Excluir</ButtonChild>
    </li>
</template>

<style scoped>
span {
    cursor: pointer;
}
.concluida {
    text-decoration: line-through;
}
</style>