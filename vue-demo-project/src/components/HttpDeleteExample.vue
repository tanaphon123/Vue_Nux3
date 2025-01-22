<script setup>
    // นำเข้า axios เพื่อใช้สำหรับส่งคำขอ HTTP
    import axios from 'axios';
    // นำเข้า ref จาก Vue (ไม่ได้ใช้งานในโค้ดนี้ แต่สามารถลบออกได้ถ้าไม่จำเป็น)
    import { ref } from 'vue';

    // ฟังก์ชันสำหรับลบโพสต์
    const handelDelete = () => {
        // ส่งคำขอ HTTP DELETE ไปที่ URL ของโพสต์ที่ต้องการลบ
        axios.delete('https://jsonplaceholder.typicode.com/posts/1') // URL สำหรับลบโพสต์ ID 1
            .then(response => {
                // แสดงข้อความใน console เมื่อโพสต์ถูกลบสำเร็จ
                console.log('Post deleted: ', response.data);
            })
            .catch(error => {
                // แสดงข้อความใน console หากเกิดข้อผิดพลาดขณะลบโพสต์
                console.error('Error deleting post: ', error);
            });
    }
</script>

<template>
    <!-- หัวข้อของหน้า -->
    <h1>Http Delete Example</h1>
    <!-- ปุ่มสำหรับเรียกใช้ฟังก์ชัน handelDelete เมื่อคลิก -->
    <button @click="handelDelete">Delete Post</button>
</template>
