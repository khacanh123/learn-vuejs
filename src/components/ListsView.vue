<template>
    <div class="lists" v-if="modelValue">
        <h1>
            <slot name="title" />
        </h1>
        <h2>
            <slot name="title2"></slot>
        </h2>
        <slot />
        <ul v-for="item in data">
            <li>{{ item.title }}</li>
        </ul>
    </div>
    <button @click="$emit('hiddenList')">Hidden List</button>
    <button @click="$emit('update:modalValue', false)">Hidden List 2</button>
</template>

<script setup>
// props
const props = defineProps({
    data: {
        type: Array,
        default: []
    },
    modelValue: {
        type: Boolean,
        default: true
    }
})
const emit = defineEmits(['hiddenList', 'update:modalValue'])
// call emit : emit('hiddenList')
</script>