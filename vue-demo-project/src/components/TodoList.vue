<script setup>
    import { ref } from 'vue'

    // สร้างตัวแปร todoList เป็น array object
    const todoList = ref([
        {id: 1, title: 'Learn Vue3 ', completed: false},
        {id: 2, title: 'Build a todo app ', completed: false},
        {id: 3, title: 'Deploy to production ', completed: false},
    ])

    // function สำหรับเพิ่ม todo list ที่เราเลือก
    const addTodo = () => {
        const title = 'new todo is ' + todoList.value.length + 1;
        const newTodo = {id: todoList.value.length + 1, title: title, completed: false};
        todoList.value.push(newTodo);     // เพิ่มค่า
    }

    // function สำหรับลบ todo ด้วย id
    const removeTodo = (id) => {
        // ลบแบบใช้ function filter
        todoList.value = todoList.value.filter(todo => todo.id !== id); // filter ใช้ค้นหาแล้วลบค่าที่ตรงกัน ใช้ใน array

        // ลบแบบ for looop ใช้ splice ในการลบ **เขียนแบบเก่า
        // for (let i = 0; i < todoList.value.length; i++) {
        //     if (todoList.value[i].id === id) {
        //         todoList.value.splice(i, 1);
        //         break;
        //     }
        // }
    }
</script>

<template>
    <ul>
        <li v-for="todo in todoList" :key="todo.id">
            {{ todo.title }}
            <button @click="removeTodo(todo.id)">Remove</button>
        </li>
    </ul>
    <button @click="addTodo">Add Todo</button>
</template>