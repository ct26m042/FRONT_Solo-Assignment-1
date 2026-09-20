<script lang="ts" setup>
import { ref } from 'vue';
import { computed } from 'vue';

const count = ref(0);
const doubleCount = computed(() => count.value * 2);

function increment() {
    count.value++;
};

function decrement() {
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