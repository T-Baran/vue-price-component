<template>
  <div class="container" :class="props.index == 1 ? 'container-dark' : ''">
    <p class="header">{{ props.data.title }}</p>
    <p class="price">
      {{ props.price ? props.data.priceA : props.data.priceM }}
    </p>
    <div class="parameters">
      <hr />
      <p>{{ props.data.param1 }}</p>
      <hr />
      <p>{{ props.data.param2 }}</p>
      <hr />
      <p>{{ props.data.param3 }}</p>
      <hr />
    </div>
    <button>LEARN MORE</button>
  </div>
</template>

<script setup>
const props = defineProps({
  data: Object,
  index: Number,
  price: Boolean,
});
</script>

<style scoped>
* {
  color: hsl(233, 13%, 49%);
}
.container {
  margin-top: 4rem;
  width: min(90vw, 400px);
  background-color: #fff;
  border-radius: 10px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  box-shadow: 0 0 25px 3px rgba(0, 0, 0, 0.1);
}

.header {
  margin-top: 2rem;
  font-size: 2rem;
}
.price {
  margin-top: 2rem;
  font-size: 4rem;
  color: hsl(232, 13%, 33%);
  display: flex;
  align-items: center;
  gap: 5px;
}
.price:before {
  content: "$";
  font-size: 2rem;
}
.parameters {
  margin-top: 2rem;
  display: flex;
  flex-direction: column;
  gap: 1rem;
  width: 80%;
  text-align: center;
}
hr {
  height: 1px;
  border-width: 0;
  background-color: hsl(234, 14%, 74%);
}
button {
  margin-top: 2rem;
  width: 80%;
  padding: 1rem 0;
  color: #fff;
  background: linear-gradient(90deg, hsl(236, 72%, 79%), hsl(237, 63%, 64%));
  outline: 1px solid inherit;
  border: none;
  border-radius: 10px;
  margin-bottom: 2rem;
  transition: 0.5s;
  cursor: pointer;
}
button:hover {
  color: hsl(237, 63%, 64%);
  background: #fff;
  outline: 1px solid hsl(237, 63%, 64%);
}
/* CHANGE THEME FOR SECOND ELEMENT */
.container-dark {
  background: linear-gradient(90deg, hsl(236, 72%, 79%), hsl(237, 63%, 64%));
  color: #fff;
}
.container-dark * {
  color: #fff;
}
.container-dark button {
  color: hsl(237, 63%, 64%);
  background: #fff;
  outline: 1px solid #fff;
}
.container-dark button:hover {
  outline: 1px solid #fff;
  background-color: inherit;
  color: #fff;
}
@media (min-width: 1100px) {
  .container-dark {
    height: 550px;
    width: min(90vw, 450px);
  }
}
</style>
