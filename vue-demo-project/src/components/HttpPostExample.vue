<script setup>
    // นำเข้า ref จาก Vue เพื่อใช้สร้างตัวแปรแบบ reactive
    import { ref } from 'vue';
    // นำเข้า axios เพื่อใช้ส่งคำขอ HTTP
    import axios from 'axios';

    // สร้างตัวแปร reactive สำหรับเก็บข้อมูล title
    const title = ref('');
    // สร้างตัวแปร reactive สำหรับเก็บข้อมูล body
    const body = ref('');
    // สร้างตัวแปร reactive สำหรับเก็บข้อมูล userId โดยตั้งค่าเริ่มต้นเป็น 1
    const userId = ref(1);

    // ฟังก์ชันที่เรียกใช้เมื่อผู้ใช้ส่งฟอร์ม
    const handleSubmit = () => {
        // ส่งคำขอ HTTP POST เพื่อสร้างโพสต์ใหม่
        axios.post('https://jsonplaceholder.typicode.com/posts', {
            // ส่งค่า title ที่ผู้ใช้กรอก
            title: title.value,
            // ส่งค่า body ที่ผู้ใช้กรอก
            body: body.value,
            // ส่งค่า userId ที่ตั้งค่าไว้
            userId: userId.value
        })
        .then(response => {
            // แสดงผลข้อมูลของโพสต์ที่สร้างสำเร็จใน console
            console.log('Post created: ', response.data);
        });
    }
</script>

<template>
    <!-- แสดงหัวข้อของฟอร์ม -->
    <h1>Http Post Example</h1>
    <!-- ฟอร์มสำหรับกรอกข้อมูลและส่งคำขอ HTTP POST -->
    <form @submit.prevent="handleSubmit">
        <!-- กล่องข้อความสำหรับกรอก title โดยใช้ v-model ผูกกับตัวแปร title -->
        <input type="text" v-model="title" placeholder="Title" required />
        <!-- กล่องข้อความสำหรับกรอก body โดยใช้ v-model ผูกกับตัวแปร body -->
        <input type="text" v-model="body" placeholder="Body" required />
        <!-- ปุ่มสำหรับส่งฟอร์ม -->
        <button type="submit">Create Post</button>
    </form>
</template>
