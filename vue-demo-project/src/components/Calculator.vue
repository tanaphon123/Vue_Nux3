<script setup>
    // นำเข้า `ref` จาก Vue เพื่อสร้างตัวแปรที่สามารถติดตามการเปลี่ยนแปลงได้ (reactive)
    import { ref } from 'vue';

    // สร้างตัวแปร `num1` เป็น reactive โดยมีค่าเริ่มต้นเป็น 0 สำหรับเก็บตัวเลขตัวแรก
    const num1 = ref(0);

    // สร้างตัวแปร `num2` เป็น reactive โดยมีค่าเริ่มต้นเป็น 0 สำหรับเก็บตัวเลขตัวที่สอง
    const num2 = ref(0);

    // สร้างตัวแปร `result` เป็น reactive โดยมีค่าเริ่มต้นเป็น 0 สำหรับเก็บผลลัพธ์ของการบวก
    const result = ref(0);

    // ฟังก์ชัน `add` ใช้บวกค่าจาก `num1` และ `num2` แล้วนำผลลัพธ์ไปเก็บใน `result`
    const add = () => {
        result.value = num1.value + num2.value;
    }

    // ฟังก์ชันลบค่าตัวเลข
    const subtract = () => {
        result.value = num1.value - num2.value;
    }

    // ฟังก์ชันคูณค่าตัวเลข
    const multiply = () => {
        result.value = num1.value * num2.value;
    }

    // ฟังก์ชันหารค่าตัวเลข
    const divide = () => {
        result.value = num1.value / num2.value;
    }
</script>

<template>
    <div>
        <!-- v-model ใน Vue ใช้สำหรับเชื่อมโยงค่าของ input, textarea, หรือ select กับตัวแปรใน JavaScript
        ทำให้ค่าที่กรอกในฟอร์มถูกอัปเดตในตัวแปรที่เชื่อมโยงทันที (Two-way Data Binding) -->
        <input type="number" v-model="num1" />
        <input type="number" v-model="num2" />   <!-- ช่องกรอกตัวเลขที่เชื่อมโยงกับตัวแปร `num2` ผ่าน v-model -->

         <!-- ปุ่มที่เมื่อถูกคลิกจะเรียกใช้ฟังก์ชัน `add` เพื่อคำนวณผลลัพธ์ -->
        <button @click="add">Add</button>
        <button @click="subtract">Subtract</button>
        <button @click="multiply">Multiply</button>
        <button @click="divide">Divide</button>

        <div>Result: {{ result }}</div>
    </div>
</template>