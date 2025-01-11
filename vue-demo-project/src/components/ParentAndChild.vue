<script setup>
    import { ref } from 'vue';

    // สร้างตัวแปรแสดง text เริ่มต้นใช้ ref เพื่อให้เปลี่ยนค่าได้
    const childMessage = ref('Hello from parent')

    // ฟังก์ชัน สำหรับ click แล้วให้เปลี่ยนข้อคามเก็บเข้าไปในตัวแปร childMessage
    const handleClick = () => {
        childMessage.value = 'Hello from child'
    }

    // ใช้ `defineEmits` เพื่อกำหนดอีเวนต์ (events) ที่ component สามารถส่งออกไปให้ parent component ได้
    // ในที่นี้กำหนดชื่ออีเวนต์คือ `myEvent`
    const emit = defineEmits(['myEvent']);

    // ฟังก์ชัน `handleClickFromParent` จะถูกเรียกเมื่อเกิดบางเหตุการณ์ใน child component
    // ใช้ `emit` เพื่อส่งอีเวนต์ `myEvent` ออกไปพร้อมข้อมูล (`Hellow from child`) ไปยัง parent component
    const handleClickFromParent = () => {
        emit('myEvent', 'Hellow from child') //eventName, message
    }

</script>

<template>
    <h2>Parent Component</h2>
    <h1>{{ childMessage }}</h1> <!-- แสดงข้อความ -->

    <!-- เมื่อ click ที่นี้ให้เปลี่ยนค่าข้อความ -->
    <button @click="handleClick">Click me</button>
    <button @click="handleClickFromParent">Click me from parent</button>

    <slot name="myHeader">Defualt Header</slot>

    <!-- slot คือพื้นที่สำหรับแทรกเนื้อหาจาก parent ลงใน child component โดย:
        เนื้อหาจาก parent จะมาแทนที่ <slot>
        สามารถใช้ name เพื่อระบุ slot เฉพาะได้ -->
</template>