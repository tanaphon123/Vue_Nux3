<script setup>
    import { ref } from 'vue';

    const isVisble = ref(true);
</script>

<template>
    <h1 v-if="isVisble">Hello If</h1>
    <h1 v-else>Hello Else</h1>
    <!-- กดปุ่เพื่อเปลี่ยน toggle เป็น true false -->
    <button @click="isVisble = !isVisble">Toggle Visibility</button>
</template>