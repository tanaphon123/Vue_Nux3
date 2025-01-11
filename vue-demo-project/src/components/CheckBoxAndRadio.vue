<script setup>
    import { ref } from 'vue'

    const isCheck = ref(false)
    const selectedOption = ref('')

    // options key and value
    const options = ref([
        {key: '100', value: 'Option 1'},
        {key: '200', value: 'Option 2'},
        {key: '300', value: 'Option 3'},
    ])
</script>

<template>
    <!-- หากติ้ก จะเปลี่ยนค่าเป็น true -->
    <input type="checkbox" v-model="isCheck"> Agree to terms and conditions
    <p>Is checked: {{ isCheck }}</p>

    <!-- loop options เอาค่าไปเก็บใน option -->
    <span v-for="option in options" :key="option.key">
        <input type="radio" v-model="selectedOption" :value="option.key" /> {{ option.value }}  <!-- แสดง input radio loop แสดง -->
    </span>
    <p>Selected option: {{ selectedOption }}</p>    <!-- แสดงค่า radio ที่เลือก -->
</template>