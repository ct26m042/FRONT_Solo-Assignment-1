<script lang="ts" setup>
import type { Todo } from '../types';

defineProps<{
    todo: Todo;
}>();

const emit = defineEmits<{
    (e: 'toggleTodo', id: number): void;
    (e: 'deleteTodo', id: number): void;
}>();

</script>

<template>
    <div>
        <input type="checkbox" :checked="todo.done" @change="emit('toggleTodo', todo.id)">
        <span>{{ todo.text }}</span>
        <button @click="emit('deleteTodo', todo.id)">Delete</button>
    </div>
</template>