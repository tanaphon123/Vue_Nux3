<script setup>
    // สร้างอาเรย์ `numbers` ที่มีตัวเลขตั้งแต่ 1 ถึง 12 สำหรับใช้เป็นข้อมูลในการวนลูปแสดงผล
    const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12]
</script>

<template>
    <!-- สร้างตาราง (table) สำหรับแสดงผลลัพธ์ -->
    <table>
        <!-- วนลูปสร้างแถวในตาราง (tr) โดยใช้ `v-for` เพื่อวนลูปผ่านตัวเลขในอาเรย์ `numbers` -->
        <!-- ใช้ `:key="number"` เป็นคีย์ที่ไม่ซ้ำกันสำหรับแต่ละแถว เพื่อช่วยให้ Vue จัดการ DOM อย่างมีประสิทธิภาพ -->
        <tr v-for="number in numbers" :key="number">
            <td>2 x {{ number }} = {{ 2 * number }}</td>
            <!-- สร้างเซลล์ในตาราง (td) เพื่อแสดงผลลัพธ์การคูณเลข 2 กับค่าของ `number` -->
        </tr>
    </table>
</template>

<!-- 
v-for คือ directive ใน Vue ที่ใช้สำหรับวนลูปเพื่อแสดงผลรายการในอาเรย์หรือวัตถุ (object)
ใช้ในกรณีที่ต้องการแสดงรายการข้อมูลที่มีหลายค่า เช่น สร้างรายการ (list) หรือสร้างองค์ประกอบ (element) ซ้ำ ๆ

โครงสร้าง
<div v-for="item in items" :key="item.id">
    {{ item.name }}
</div>

-->
