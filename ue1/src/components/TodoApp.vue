<script lang="ts" setup>
import { ref } from 'vue';


interface Todo {
    id: number;
    text: string;
    done: boolean;
}

const todos = ref<Array<Todo>>([]);

function addTodo(text: string): void {
    todos.value.push({
        id: todos.value.length + 1,
        text: text,
        done: false,
    });
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
        
    </div>
</template>