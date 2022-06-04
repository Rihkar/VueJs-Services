<template>
  <div class="container">
    <h1>Services</h1>
    <div
      class="service-box"
      v-for="{ serviceType, price, selected } in services"
      :key="serviceType"
      @click="
        selected = !selected;
        selected ? (totalPrice += price) : (totalPrice -= price);
      "
      :class="{ serviceSelected: selected }"
    >
      <span class="test2">{{ serviceType }}</span>
      <span class="test2">{{ `$${price.toFixed(2)}` }}</span>
    </div>
    <div class="total">
      <span>Total:</span>
      <span>{{ totalPrice.toFixed(2) }}</span>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "HomeView",
  data: () => ({
    services: [
      {
        serviceType: "Web Development",
        price: 300,
        selected: false,
      },
      {
        serviceType: "Design",
        price: 400,
        selected: false,
      },
      {
        serviceType: "Integration",
        price: 250,
        selected: false,
      },
      {
        serviceType: "Training",
        price: 220,
        selected: false,
      },
    ],
    totalPrice: 0,
  }),
});
</script>
