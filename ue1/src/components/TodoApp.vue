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

</script>

<template>
    <div>
        <h1>Todo App</h1>
    </div>
</template>