<script setup>
    // ประกาศตัวแปรใช้ `defineProps` เพื่อรับค่าที่ถูกส่งมาจาก component แม่ (Parent Component)
    const props = defineProps({
        text: {
            // ระบุว่า prop `text` จะต้องเป็นชนิด String
            type: String,

            // ระบุว่า prop `text` นี้ต้องส่งค่ามาเสมอ ถ้าไม่มีการส่งค่าจะเกิดข้อผิดพลาด
            required: true
        }
    })
</script>

<template>
    <!-- แสดงค่าที่ถูกส่งมาผ่าน prop `text` ในปุ่ม (button) -->
    <button>{{ props.text }}</button>
</template>
