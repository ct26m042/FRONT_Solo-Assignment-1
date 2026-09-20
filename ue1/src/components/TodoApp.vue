

<script lang="ts" setup>
import { ref } from 'vue';

interface Todo {
    id: number;
    text: string;
    completed: boolean;
}

const todos = ref<Todo[]>([]);

</script>

<template>
    <div>
        <h1>Todo App</h1>
    </div>
</template>