<script setup>
    import { ref } from 'vue';

    // ประกาศตัวแปร สามารเปลี่ยนค่าได้
    const name = ref('');   // เก็บค่าที่เรากรอกจาก input
    const nameError = ref('');  // สำหรับเก็บค่า error

    // ฟังก์ชัน check ค่าความยาวของค่าที่เรากรอก หากกด submit
    const handleSubmit = () => {
        if (name.value.length < 3) {    // หากค่าที่เรากรอกมามีควมยาวน้อยก่า 3 ตัวอักษร ให้แสดง error
            nameError.value = 'Name must be at least 3 characters'
        } else {
            nameError.value = ''    // clear nameError value
        }
    }
</script>

<template>
    <form @submit.prevent="handleSubmit">
        <input type="text" v-model="name" placeholder="Enter your name">    <!-- input กรอกค่า -->
        <p>{{ nameError }}</p> <!-- แสดง error -->
        <button type="submit">Submit</button>
    </form>
</template>