<script setup>
    // นำเข้า `ref` จาก Vue เพื่อใช้สำหรับสร้างตัวแปรที่สามารถติดตามการเปลี่ยนแปลงของค่าได้ (reactive)
    import { ref } from 'vue'; 

    // สร้างตัวแปร `count` เป็นค่าที่สามารถเปลี่ยนแปลงได้ (reactive) และตั้งค่าเริ่มต้นเป็น 0
    const count = ref(0);
</script>

<template>
    <!-- สร้างปุ่มที่เมื่อถูกคลิกจะเพิ่มค่าของ `count` ขึ้น 1 -->
    <button @click="count++">Upper</button>

    <!-- สร้างปุ่มที่เมื่อถูกคลิกจะลดค่าของ `count` ลง 1 -->
    <button @click="count--">Lower</button>

    <!-- แสดงค่าของตัวแปร `count` บนหน้าเว็บในรูปแบบข้อความ -->
    <div>Counter: {{ count }}</div>
</template>
