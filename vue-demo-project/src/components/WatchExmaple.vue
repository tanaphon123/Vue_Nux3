<script setup>
    import { ref, watch } from 'vue';

    const price = ref(100);
    const quantity = ref(2);
    const total = ref(0);

    // เฝ้าดูแล้วค่อยเปลี่ยนค่า ต้องมีการเปลี่ยนค่าตัวแปรก่อนค่อยจะคำนวนทำใหน function
    watch([price, quantity], ([newPrice, newQuantity]) => {
       total.value = newPrice * newQuantity;
    })

</script>

<template>
    <h1>Watch Example</h1>
    <p>Price: {{ price }}</p>
    <input type="number" v-model="price" />

    <p>quantity: {{ quantity }}</p>
    <input type="number" v-model="quantity" />

    <p>Total: {{ total }}</p>
</template>