<script setup>
  import { ref, computed } from "vue"
  import ButtonComponent from "./ButtonComponent.vue"

  const packSize = ref(7)
  const quantity = ref(1)
  const price = ref(132.30/7)
  let deafultPrice = computed(() => {
    return `$${(price.value * packSize.value * quantity.value).toFixed(2)}`
  })

  const dec = () => {
    if(quantity.value > 1){
      quantity.value--
    }
  }

</script>

<template>
  <div class="h-screen p-[80px] overflow-hidden">
    <h3 class="special-h3 text-[50px] ">Special Offer </h3>
    <div class="flex gap-2 p-5">
      <div>
        <img src="/special1.png" class="max-w-[580px] h-[720px]"/>
      </div>
      <div>
        <img src="/special2.png" class="w-[580px] h-[720px]"/>
      </div>
      <div class="h-full pl-[60px]">
        <span class="text-[40px] h3-font">Espresso Roast Blend (Whole Bean, Dark Roast)</span>
        <p class="text-red-600 text-[30px]">{{ deafultPrice }}</p>
        <div class="border-y-gray-300  border-y-2 border-solid p-5 my-10">
          <p>Size: Pack {{ packSize }}</p>
          <div class="flex gap-2 m-5">
            <div class="border-2 border-gray-200 p-3" @click="packSize = 7">Size 7</div>
            <div class="border-2 border-gray-200 p-3" @click="packSize = 10">Size 10</div>
            <div class="border-2 border-gray-200 p-3" @click="packSize = 15">Size 15</div>
          </div>
        </div>
        <div class="my-10">
          <p>Quantity:</p>
          <div class="border-gray-300 border-2 border-solid p-5 m-5 max-w-[150px] flex justify-center items-center">
            <p @click="dec">-</p>
            <p class="mx-10">{{ quantity }}</p>
            <p @click="quantity++">+</p>
          </div>
        </div>
          <ButtonComponent color = "primary" style="border: 1px solid black"> Checkout </ButtonComponent>
      </div>
    </div>
  </div>
</template>

<style>
  .special-h3{
    font-style: italic;
    font-weight: 400;
    font-family: 'Amiri', sans;
    color: #00312d;
  }
  .h3-font{
    font-family: "Amiri", sans;
    font-style: italic;
    font-weight: 400;
  }
</style>
