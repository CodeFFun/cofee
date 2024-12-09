<script setup>
import ButtonComponent from "./ButtonComponent.vue";
import CardComponent from "./CardComponent.vue";

const data = [
  {
    image: "/img1.png",
    caption: "BEST ELLA ROASTED COFFEE",
    price: "$52.40"
  },
  {
    image: "/img2.png",
    caption: "BEST ELLA ROASTED COFFEE",
    price: "$32.40"
  },
  {
    image: "/img3.png",
    caption: "BEST ELLA ROASTED COFFEE",
    price: "$87.99"
  },
  {
    image: "/img4.png",
    caption: "BEST ELLA ROASTED COFFEE",
    price: "$12.40"
  },
];
</script>

<template>
  <section class="display-category">
    <div class="display-category-head">
      <h3>New Arrivals</h3>
      <div style="display: flex; gap: 5px;">
      </div>
    </div>
    <div style="display: flex; gap: 10px; padding: 0 80px; margin: 10px 0;">
        <div
          class="display-category-card-container"
          v-for="coffee in data"
          :key="coffee.image"
        >
          <CardComponent :image="coffee.image" />
          <ButtonComponent color="primary" style="width: 100%; border: 1px solid black">Add To Cart: {{ coffee.price }}</ButtonComponent>
        </div>

    </div>
  </section>
</template>

<style>
.display-category {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 80px 80px 90px 80px;
}

.display-category-head {
  display: flex;
  width: 100%;
  align-items: center;
  justify-content: space-between;
}

.display-category-head h3 {
  font-family: "Amiri", serif;
  font-size: 50px;
  font-weight: 400;
  color: #00312d;
  font-style: italic;
}

.display-category-card-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 100%;
  gap: 10px;
}
</style>
