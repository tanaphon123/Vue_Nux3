<script setup>
    import { ref } from 'vue';

    const selectedOption = ref('')
    const options = ['Option 1', 'Option 2', 'Option 3']
</script>

<template>
    <select v-model="selectedOption">
        <option v-for="option in options" :key="option">{{ option }}</option> <!-- loop แสดง select -->
    </select>
    <p>Selected option: {{ selectedOption }}</p>
</template>