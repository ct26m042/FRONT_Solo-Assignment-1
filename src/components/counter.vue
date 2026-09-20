<script lang="ts" setup>
import { ref } from 'vue';
import { computed } from 'vue';

const count = ref<number>(0);
const doubleCount = computed<number>(() => count.value * 2);

function increment(): void {
    count.value++;
};

function decrement(): void {
    if (count.value > 0) {
    count.value--;
    }
};
</script>

<template>
    <div>
        <button @click="increment()">Increment</button>
        <button @click="decrement()">Decrement</button>
        <p>Count: {{ count }}</p>
        <p>Double Count: {{ doubleCount }}</p>
    </div>
</template>