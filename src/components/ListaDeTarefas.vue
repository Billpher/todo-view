<script setup>
const props = defineProps(['tarefas']);
</script>

<template>
    <ul class="list-group mt-4">
        <li class="list-group-item" v-for="tarefa in props.tarefas">
            <input @change="e => tarefa.finalizado = e.target.checked" :checked="tarefa.finalizado" :id="tarefa.titulo"
                type="checkbox">
            <label :for="tarefa.titulo" class="ms-3" :class="{ done: tarefa.finalizado }">
                {{ tarefa.titulo }}
            </label>
        </li>
    </ul>
</template>

<style scoped>
.done {
    text-decoration: line-through;
}
</style>