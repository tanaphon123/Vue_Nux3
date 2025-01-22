<script setup>
    // การดึงข้อมูลจาก api มาแสดงในหน้าเว็บด้วย axios
    import { ref } from 'vue';  
    import axios from 'axios';  // import axios

    const items = ref([]);  // ประกาศตัวแปร items เป็นค่าคงที่แต่ใช้ ref เพื่อให้เปลี่ยนค่าได้

    axios.get('https://jsonplaceholder.typicode.com/posts') // ใช้ axios ในการ get data มาจาก api
        .then(response => {
            items.value = response.data;    // เมื่อคำขอสำเร็จ นำข้อมูลที่ได้จาก api respponse.data ไปเก็บไว้ที่ตัวแปร items.value
        });

</script>

<template>
    <h1>Http Get Example</h1>
    <ul>
        <!-- loop ข้อมูลมาแสดงเป็น list -->
        <li v-for="item in items" :key="item.id">{{ item.title }}</li>      
    </ul>
</template>