<script setup>
    import { ref, onMounted } from 'vue'

    // เดือนเริ่มต้นเป็น january
    const month = ref('January')

    // function สำหรับเปลี่ยนค่า เดือน
    onMounted(() => {
        month.value = 'February'
    });
</script>

<template>
    <p>Month: {{ month }}</p>  <!-- แสดงค่าเดือน -->
</template>