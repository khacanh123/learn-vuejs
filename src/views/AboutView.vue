<template>
  <div class="about">
    <h1>{{ message }}</h1>
    <br />
    <input v-model="message" />

    <br />
    <h2>{{ count }}</h2>
    <input type="text" v-model="count">
  </div>
</template>

<script>
import { watch } from 'vue'
export default {
  data() {
    return {
      message: 'Hello world!'
    }
  },
  methods: {
    updateMessage() {
      this.message = 'tttttt'
    }
  },
  created() {
    watch(() => this.message, (newVal, oldVal) => {
      console.log('====================================');
      console.log(newVal, oldVal);
      console.log('====================================');
    })
  },
  // mounted() {
  //   console.log('====================================');
  //   console.log('mounted');
  //   console.log('====================================');
  // },
  // unmounted() {
  //   console.log('unmounted')
  // },
  // updated() {
  //   console.log('====================================');
  //   console.log('updated');
  //   console.log('====================================');
  // }
}
</script>

<script setup>
/**
 import
 */
import { ref, reactive } from 'vue';

/**
 counter
 */
const count = ref(0);

const increaseCounter = () => count.value++
const decreaseCounter = () => count.value--

/**
 intro me
 */
const data = reactive({
  name: 'Anh Hin',
  age: 23
})

const changeData = (newName, newAge) => {
  data.name = newName;
  data.age = newAge;
}
</script>
<style>
@media (min-width: 1024px) {}
</style>
