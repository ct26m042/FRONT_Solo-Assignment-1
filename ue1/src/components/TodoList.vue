<script lang="ts" setup>
import type { Todo } from '../types';


defineProps<{
    todos: Array<Todo>;
}>();

const emit = defineEmits<{
    (e: 'toggleTodo', id: number): void;
    (e: 'deleteTodo', id: number): void;
}>();

</script>

<template>
    <div>
        <h1>Todo List</h1>
        <TodoItem v-for="todo in todos" :key="todo.id" :todo="todo" @toggleTodo="emit('toggleTodo', todo.id)" @deleteTodo="emit('deleteTodo', todo.id)" />
    </div>
</template>
