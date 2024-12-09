<script setup>
  import { ref, computed, onBeforeMount, watch } from "vue"
  import { useRoute } from 'vue-router'
 import ButtonComponent from "@/components/ButtonComponent.vue";
 import NavbarComponent from "@/components/NavbarComponent.vue";

  const route = useRoute()
  const data = ref([])
  const id = route.params.id
 onBeforeMount(async () => {
  const response  = await fetch(`https://fake-coffee-api.vercel.app/api/${id}`)
   data.value = await response.json()
   console.log(data.value[0].price)
 })
  const packSize = ref(7)
  const quantity = ref(1)
  const price = ref(0)
  // const price = ref(10)
  let deafultPrice = computed(() => {
    return `$${(price.value * packSize.value * quantity.value).toFixed(2)}`
  })
  watch(data, (newData) => {
      if (newData.length > 0) {
        price.value = newData[0].price  // Update price when data is fetched
      }
    })

  const dec = () => {
    if(quantity.value > 1){
      quantity.value--
    }
  }

</script>

<template>
  <NavbarComponent />
  <div class="h-screen p-[80px] overflow-hidden">
    <div class="flex gap-2 p-5">
      <div>
        <img :src="data[0].image_url" class="max-w-[1060px] max-h-[700px]"/>
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
