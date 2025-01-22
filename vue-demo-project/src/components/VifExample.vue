<script setup>
    import { ref } from 'vue'

    // ประกาศตัวแปร isVisible มีค่าเป็น true
    const isVisible = ref(true);
</script>

<template>
    <!-- ถ้าหาก viSible เป็น ture ก็ให้แสดง Hello World -->
    <h1 v-if="isVisible">Hellow World</h1>
</template>