<script setup>
    import { ref } from 'vue'

    const textbox = ref(null) // ใช้ ref กับ element ที่ต้องการจะจับคู่

    const foucsTextbox = () => {
        textbox.value.focus(); // เรียกใช้ focus() เมื่อฟังก์ชันถูกเรียกใช้
    }
</script>

<template>
    <input type="text" ref="textbox">
    <button @click="foucsTextbox">Focus Textbox</button>    <!-- เมื่อ click button function จะถูกเรียกใช้และแสดง focus -->
</template>