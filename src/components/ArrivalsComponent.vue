<script setup>
import ButtonComponent from "./ButtonComponent.vue";
import CardComponent from "./CardComponent.vue";

const data = [
  {
    image: "/collection-list-1.png",
    caption: "BEST ELLA ROASTED COFFEE",
  },
  {
    image: "/collection-list-2.png",
    caption: "BEST ELLA ROASTED COFFEE",
  },
  {
    image: "/collection-list-3.png",
    caption: "BEST ELLA ROASTED COFFEE",
  },
  {
    image: "/collection-list-4.png",
    caption: "BEST ELLA ROASTED COFFEE",
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
          <ButtonComponent color="primary" style="width: 100%;">Notify Me</ButtonComponent>
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
