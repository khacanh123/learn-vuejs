<template>
    <div class='grid grid-cols-2 gap-2 mt-2 mb-2'>
        <div class='border border-[#dfdfdf] rounded-3xl flex items-center px-2 py-2 cursor-pointer mb-2'
            v-bind:id="'id-answer' + item.answer_id" v-for="item in answer" @click="choiceAnswer(item.answer_id)">
            <MathJax v-bind:math="item.answer_content" />
        </div>

    </div>
</template>

<script setup>
import MathJax from './MathJax.vue';
const props = defineProps({
    answer: {
        type: Array,
        default: []
    }
})
const emit = defineEmits(['check'])
const choiceAnswer = (idAnswer) => {

    props.answer.map((k, index) => {
        if (k.answer_id === idAnswer) {
            const element = document.getElementById('id-answer' + k.answer_id);
            if (element !== null) {
                element.style.border = '2px solid #2691FF';
            }
        } else {
            const element = document.getElementById('id-answer' + k.answer_id);
            if (element !== null) {
                element.style.background = '#fff';
                element.style.border = '1px solid #dfdfdf';
                element.style.color = '#000';
            }
        }
    })
    emit('check', idAnswer)
}
const checkBoolean = () => {
    console.log('====================================');
    console.log(typeof true);
    console.log('====================================');
}
</script>