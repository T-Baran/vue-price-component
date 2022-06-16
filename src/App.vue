<template>
  <div class="container-header">
    <HeaderComponentVue @checked="updateChecked($event)" />
  </div>
  <div class="container-plan">
    <PlanComponentVue
      v-for="(data, i) in datas"
      :key="i"
      :data="data"
      :index="i"
      :price="state.isCheckedPrice"
    />
  </div>
</template>

<script setup>
import HeaderComponentVue from "./components/HeaderComponent.vue";
import PlanComponentVue from "./components/PlanComponent.vue";

import { reactive } from "vue";

const state = reactive({
  isCheckedPrice: true,
});

const updateChecked = (value) => {
  state.isCheckedPrice = value;
};

const datas = [
  {
    title: "Basic",
    priceA: 199.99,
    priceM: 19.99,
    param1: "500 GB Storage",
    param2: "2 Users Allowed",
    param3: "Send up to 3 GB",
  },
  {
    title: "Professional",
    priceA: 249.99,
    priceM: 24.99,
    param1: "1 TB Storage",
    param2: "5 Users Allowed",
    param3: "Send up to 10 GB",
  },
  {
    title: "Master",
    priceA: 399.99,
    priceM: 39.99,
    param1: "2 TB Storage",
    param2: "10 Users Allowed",
    param3: "Send up to 20 GB",
  },
];
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Montserrat", sans-serif;
}
body {
  width: 100vw;
  height: 100vh;
  background-color: hsl(240, 78%, 98%);
  position: relative;
}
.container-plan {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-bottom: 2rem;
}

@media (min-width: 1100px) {
  .container-header {
    margin-bottom: 2rem;
  }

  .container-plan {
    flex-direction: row;
    justify-content: center;
    align-items: center;
  }
}
</style>
