<script lang="ts" setup>
import { ref } from 'vue';
import type { Todo } from '../types';
import TodoList from './TodoList.vue';

const todos = ref<Array<Todo>>([]);
const newTodo = ref<string>('');

function addTodo(): void {
    const text: string = newTodo.value.trim();
    
    if (!text) {
        return;
    }
    
    todos.value.push({
        id: todos.value.length + 1, // Date.now() ?
        text: text,
        done: false,
    });

    newTodo.value = '';
}

function toggleTodo(id: number): void {
    const todo = todos.value.find((todo: Todo) => todo.id === id);
    if (todo) {
        todo.done = !todo.done;
    }
}

function deleteTodo(id: number): void {
    todos.value = todos.value.filter((todo: Todo) => todo.id !== id);
}

</script>

<template>
    <div>
        <h1>Todo App</h1>
        <TodoList :todos="todos" @toggleTodo="toggleTodo" @deleteTodo="deleteTodo" />
        <input type="text" v-model="newTodo" @keyup.enter="addTodo">
        <button @click="addTodo">Add</button>
    </div>
</template>