<template>
    <div class="two-way">
        <h3>Nam sinh: {{ info.yearOfBirth }}</h3>
        <input type="number" v-model="info.yearOfBirth" />

        <h3>Tuoi hien tai: {{ info.age }}</h3>
        <h3>{{ ChanLe }}</h3>
    </div>
</template>

<script setup>
import { reactive, watch, computed } from 'vue';

const date = new Date()

const info = reactive({
    name: 'Nguyen Khac Anh',
    yearOfBirth: 0,
    age: 0
})

watch(() => info.yearOfBirth, (newVal, oldVal) => {
    if (date.getFullYear() < parseInt(newVal)) {
        alert('Nam sinh lon hon nam hien tai!')
        info.yearOfBirth = oldVal
    } else {
        info.age = date.getFullYear() - parseInt(newVal)
    }
})

const ChanLe = computed(() => {
    if (info.yearOfBirth % 2 === 0) return 'Nam chan';
    else return 'Nam le'
})

</script>