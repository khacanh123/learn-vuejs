<template>
    <div>
        <h1>Lifescycle</h1>
        <br />
        <h4>{{ count }} click</h4>
        <button ref="myButton">Click me</button>
        <button id="myBtn" @click="showModal = true">Open Modal</button>
        <br />
        <!-- The Modal -->
        <div id="myModal" class="modal" v-if="showModal">

            <!-- Modal content -->
            <div class="modal-content">
                <span class="close" @click="showModal = false">&times;</span>
                <p>Some text in the Modal..</p>
            </div>

        </div>
        <h1>ChildComponent</h1>

        <Lists v-bind:data="data" v-if="showList" @hiddenList="showList = false">
            <template #title>title nè</template>
            <template v-slot:title2>title2 nè</template>
            <h3>Đây là nội dung slot</h3>
        </Lists>
    </div>
    <div>
        <label for=""> Show content welcome <input type="checkbox" v-model="showContent" /></label>

    </div>
    <component :is="showContent ? WelcomeItem : HelloWorld">

    </component>
    <MathJax math="\[
                    \left( \sum_{k=1}^n a_k b_k \right)^{\!\!2} \leq
                     \left( \sum_{k=1}^n a_k^2 \right) \left( \sum_{k=1}^n b_k^2 \right)
                    \]" />
    <h1 class="text-3xl font-bold underline">
        Hello world!
    </h1>
</template>

<style>
.modal {
    position: fixed;
    /* Stay in place */
    z-index: 1;
    /* Sit on top */
    left: 0;
    top: 0;
    width: 100%;
    /* Full width */
    height: 100%;
    /* Full height */
    overflow: auto;
    /* Enable scroll if needed */
    background-color: rgb(0, 0, 0);
    /* Fallback color */
    background-color: rgba(0, 0, 0, 0.4);
    /* Black w/ opacity */
}

/* Modal Content/Box */
.modal-content {
    background-color: #fefefe;
    margin: 15% auto;
    /* 15% from the top and centered */
    padding: 20px;
    border: 1px solid #888;
    width: 80%;
    /* Could be more or less, depending on screen size */
}

/* The Close Button */
.close {
    color: #aaa;
    float: right;
    font-size: 28px;
    font-weight: bold;
}

.close:hover,
.close:focus {
    color: black;
    text-decoration: none;
    cursor: pointer;
}
</style>
<script setup>
import { ref, onBeforeMount, onMounted, onBeforeUpdate, onUpdated } from 'vue';
import Lists from '@/components/ListsView.vue'
import HelloWorld from '@/components/HelloWorld.vue'
import WelcomeItem from '@/components/WelcomeItem.vue'
import MathJax from '../components/MathJax.vue';

const myButton = ref(null)
const count = ref(0)
const showModal = ref(false)
const showList = ref(true);
const data = ref([
    {
        title: 'đi học về',
    },
    {
        title: 'đi học về cccc',
    },
    {
        title: 'đi chơi về',
    },
])
const showContent = ref(false)

onBeforeMount(() => {
    const response = fetch('https://jsonplaceholder.typicode.com/todos/1')
        .then(response => response.json())
        .then(json => console.log(json))
})

onMounted(() => {
    console.log('run onMounted');
    // Thiết lập sự kiện lắng nghe cho nút
    myButton.value.addEventListener('click', handleClick);
})
onBeforeUpdate(() => {
    console.log('beforeUpdate');
})
onUpdated(() => {
    console.log('updated');
})

const handleClick = () => {
    count.value++
}

</script>