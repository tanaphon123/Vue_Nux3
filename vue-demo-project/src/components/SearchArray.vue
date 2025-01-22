<script setup>
    // นำเข้า `ref` และ `computed` จาก Vue เพื่อใช้ใน Composition API
    import { ref, computed } from 'vue';
    
    // ประกาศ `items` เป็นตัวแปรแบบ reactive เก็บค่าเป็น array object
    const items = ref([
        { id: 1, name: 'Item 1' },
        { id: 2, name: 'Item 2' },
        { id: 3, name: 'Item 3' },
    ]);

    // ประกาศ `search` เป็นตัวแปรแบบ reactive ใช้สำหรับเก็บค่าข้อความค้นหาที่ผู้ใช้พิมพ์ใน input
    const search = ref('');

    // ใช้ computed property เพื่อสร้างรายการใหม่ที่กรองตามคำค้นหาใน `search`
    // ฟังก์ชัน `filter` จะตรวจสอบว่า `item.name` มีคำที่ตรงกับค่าของ `search` หรือไม่
    const filteredItems = computed(() => {
        return items.value.filter(item => item.name.includes(search.value));
    });
</script>

<template>
    <!-- ช่องป้อนข้อมูลที่ผูกกับตัวแปร `search` ด้วย v-model -->
    <!-- เมื่อผู้ใช้พิมพ์ข้อความในช่อง input ค่าใน `search` จะเปลี่ยนตาม -->
    <input type="text" v-model="search" placeholder="Search...">

    <!-- แสดงรายการที่ถูกกรองจาก `filteredItems` -->
    <!-- ใช้ `v-for` เพื่อวนลูปแสดงรายการ และ `:key` ระบุ `id` เพื่อเพิ่มประสิทธิภาพ -->
    <ul>
        <li v-for="item in filteredItems" :key="item.id">{{ item.name }}</li>
    </ul>
</template>


<!-- computed ใช้สร้าง computed property ใน Vue ซึ่งเป็นค่าที่คำนวณได้จาก reactive data
    มีความสามารถในการ cache (แคช) ผลลัพธ์:
    ถ้าข้อมูลที่ใช้คำนวณไม่มีการเปลี่ยนแปลง ค่าใน computed จะไม่ถูกคำนวณใหม่
    ถ้าข้อมูลเปลี่ยนแปลง computed จะคำนวณค่าใหม่โดยอัตโนมัติ
 -->
