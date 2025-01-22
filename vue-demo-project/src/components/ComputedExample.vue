<script setup>
    import { ref, computed } from 'vue';

    const price = ref(100); // ประกาศตัวแปร price เป็น const แต่ใช้ ref เปลี่ยนค่าได้
    const quantity = ref(2);

    const total = computed(() => {  // คำนวนค่าใหม่โดยอัตโนมัติ
        return price.value * quantity.value;
    });
</script>

<template>
    <h1>Computed Example</h1>
    <p>Price: {{ price }}</p>
    <input type="number" v-model="price" />

    <p>quantity: {{ quantity }}</p>
    <input type="number" v-model="quantity" />

    <p>Total: {{ total }}</p>
</template>