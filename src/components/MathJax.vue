<template>
    <div ref="idDom" class=''>
        <div v-html="math" class=''></div>
    </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';
const idDom = ref(null)
const props = defineProps({
    math: {
        default: '',
        type: String,
    }

})
onMounted(() => {
    if (window.MathJax) {
        window.MathJax.typesetPromise([idDom.value]).then(() => { });
    }
})
</script>