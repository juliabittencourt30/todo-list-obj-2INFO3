<script setup>
    defineProps(['id', 'descricao', 'status'])
    defineEmits(['editar', 'excluir'])
</script>

<template>
    <li>
        <span :class="{concluida: status === 'concluida'}">
        {{ descricao }}
        </span>
        <ButtonChild @clique="$emit('editar', id)">Editar</ButtonChild>
        <a href="#" @click.prevent="$emit('excluir', id)">Excluir</a>
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