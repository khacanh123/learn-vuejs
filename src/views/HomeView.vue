

<template>
  <div class="home">
    <div>
      <h3>{{ data.title }}</h3>
      <button @click="decreaseCounter" class="btn">-</button>
      <span class="counter">{{ data.count }}</span>
      <button @click="increaseCounter" class="btn">+</button>
    </div>
    <input v-model="data.title" />
    <p>result is {{ odddOrEven }}</p>
  </div>
</template>
<!--
<script>
// export default {
//   data() {
//     return {
//       counter: 0
//     }
//   },
//   methods: {
//     increaseCounter() {
//       this.counter++;
//     },
//     decreaseCounter() {
//       this.counter--;
//     }
//   }
// }
import { ref } from 'vue';
// cách 1: 
export default {
  setup() {
    const counter = ref(0)

    const increaseCounter = () => {
      counter.value++;
    }

    const decreaseCounter = () => {
      counter.value--;
    }

    return {
      counter,
      increaseCounter,
      decreaseCounter
    }
  }
}
</script>

<script setup>
// cách 2
import { ref } from 'vue';
const counter = ref(0)

const increaseCounter = () => {
  counter.value++;
}

const decreaseCounter = () => {
  counter.value--;
}
</script>!-->
<script setup>
import { reactive, computed, watch } from 'vue';

const data = reactive({
  title: 'Anh Hin',
  count: 0
})

watch(() => data.count, (newVal, oldVal) => {
  if (newVal === 5) alert('ttttt')
})
const odddOrEven = computed(() => {
  if (data.count % 2 === 0) return 'odd'
  return 'even'
})
const increaseCounter = () => {
  data.count++
}
const decreaseCounter = () => {
  data.count--
}
</script>
<style>
.home {
  text-align: center;
  padding: 20px;
}

.btn,
.counter {
  font-size: 40px;
  margin: 20px;
}
</style>
