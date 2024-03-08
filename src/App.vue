<template>
  <div class="container">
    <h1>สีสันบันเทิง</h1>
    <div class="colors">
      <div class="choice">
        <div class="color" :style="{ 'background-color': '#' + choice1.HEX }">
          <h2 class="colorName">{{ choice1.CODE }}</h2>
        </div>
      </div>
      <div class="choice">
        <div class="color" :style="{ 'background-color': '#' + choice2.HEX }">
          <h2 class="colorName">{{ choice2.CODE }}</h2>
        </div>
      </div>
      <div class="choice">
        <div class="color" :style="{ 'background-color': '#' + choice3.HEX }">
          <h2 class="colorName">{{ choice3.CODE }}</h2>
        </div>
      </div>
      <div class="choice">
        <div class="color" :style="{ 'background-color': '#' + choice4.HEX }">
          <h2 class="colorName">{{ choice4.CODE }}</h2>
        </div>
      </div>
    </div>
    <h2 class="btn" @click="random()">สุ่ม</h2>
  </div>
</template>

<script setup>
import { computed, ref } from 'vue';
import Colors from './Colors.json';

const seed = ref([Math.random(), Math.random(), Math.random(), Math.random()])
const choice1 = computed(() => Colors[Math.floor(seed.value[0] * (479 - 0 + 1) + 0)])
const choice2 = computed(() => Colors[Math.floor(seed.value[1] * (479 - 0 + 1) + 0)])
const choice3 = computed(() => Colors[Math.floor(seed.value[2] * (479 - 0 + 1) + 0)])
const choice4 = computed(() => Colors[Math.floor(seed.value[3] * (479 - 0 + 1) + 0)])

const random = () => {
  seed.value = [Math.random(), Math.random(), Math.random(), Math.random()]
}
</script>

<style scoped></style>