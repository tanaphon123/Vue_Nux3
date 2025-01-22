<script setup>
    // นำเข้า axios เพื่อใช้สำหรับส่งคำขอ HTTP
    import axios from 'axios';
    // นำเข้า ref จาก Vue เพื่อสร้างตัวแปรแบบ reactive
    import { ref } from 'vue';

    // สร้างตัวแปร reactive สำหรับเก็บข้อมูล title
    const title = ref('');
    // สร้างตัวแปร reactive สำหรับเก็บข้อมูล body
    const body = ref('');
    // สร้างตัวแปร reactive สำหรับเก็บข้อมูล userId และตั้งค่าเริ่มต้นเป็น 1
    const userId = ref(1);

    // ฟังก์ชันที่เรียกใช้เมื่อผู้ใช้ส่งฟอร์ม
    const handleSubmit = () => {
        // สร้าง payload เป็นวัตถุที่เก็บค่าข้อมูล title, body และ userId
        const payload = {
            title: title.value, // เก็บค่าจากตัวแปร title
            body: body.value, // เก็บค่าจากตัวแปร body
            userId: userId.value // เก็บค่าจากตัวแปร userId
        };
        // ส่งคำขอ HTTP PUT เพื่ออัปเดตข้อมูลโพสต์ที่มี ID เป็น 1
        axios.put('https://jsonplaceholder.typicode.com/posts/1', payload)
            .then(response => {
                // แสดงผลข้อมูลของโพสต์ที่ถูกอัปเดตสำเร็จใน console
                console.log('Post updated: ', response.data);
            });
    }
</script>

<template>
    <!-- หัวข้อของหน้า -->
    <h1>Http Put Example</h1>
    <!-- ฟอร์มสำหรับกรอกข้อมูลและส่งคำขอ HTTP PUT -->
    <form @submit.prevent="handleSubmit">
        <!-- กล่องข้อความสำหรับกรอก title โดยใช้ v-model ผูกกับตัวแปร title -->
        <input type="text" v-model="title" placeholder="Title" required />
        <!-- กล่องข้อความสำหรับกรอก body โดยใช้ v-model ผูกกับตัวแปร body -->
        <input type="text" v-model="body" placeholder="Body" required />
        <!-- ปุ่มสำหรับส่งฟอร์ม -->
        <button type="submit">Update Post</button>
    </form>
</template>
