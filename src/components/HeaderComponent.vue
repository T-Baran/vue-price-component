<template>
  <h1>Our Pricing</h1>
  <div class="plan-select">
    <p>Annually</p>
    <input
      class="input-select"
      type="checkbox"
      v-model="state.checked"
      @click="$emit('checked', state.checked)"
    />
    <p>Monthly</p>
  </div>
</template>

<script setup>
import { reactive } from "vue";

defineEmits(["checked"]);

const state = reactive({
  checked: false,
});
</script>

<style scoped>
* {
  color: hsl(233, 13%, 49%);
}

h1 {
  text-align: center;
  padding-top: 4rem;
}
.plan-select {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 1rem;
  position: relative;
  margin-top: 2rem;
}
.input-select {
  position: relative;
  width: 60px;
  height: 30px;
  -webkit-appearance: none;
  background: linear-gradient(90deg, hsl(236, 72%, 79%), hsl(237, 63%, 64%));
  outline: none;
  border-radius: 20px;
  box-shadow: inset 0 0 5px rgba(0, 0, 0, 0.2);
  transition: 0.5s;
  cursor: pointer;
}
.input-select:checked {
  background-color: green;
}
.input-select::before {
  content: "";
  position: absolute;
  width: 22px;
  height: 22px;
  left: 4px;
  top: 4px;
  border-radius: 50%;
  background-color: #fff;
  transition: 0.5s;
}
.input-select:checked::before {
  left: 34px;
}
.input-select:hover {
  filter: saturate(0.5);
}
</style>
