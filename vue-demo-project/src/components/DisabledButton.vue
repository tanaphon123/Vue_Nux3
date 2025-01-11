<script setup>
    import { ref } from 'vue';

    // ปรรกาศตัวแปร กำนหดค่าให้เป็น false ในตอนเริ่มต้น
    const isDisabled = ref(false);
</script>

<template>
    <!-- checkbox เพื่อเปลี่ยนค่า isDisabled -->
    <input type="checkbox" v-model="isDisabled" /> Disabled button
    <button :disabled="isDisabled">Click me</button>    <!-- หากเลือก checkbox จะกำหนดให้ button เป็น disabled -->
    <p>Is disabled: {{ isDisabled }}</p> <!-- แสดงค่า isDisabled true, false -->
</template>