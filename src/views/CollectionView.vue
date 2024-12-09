<script setup>
import {onMounted, ref, computed} from 'vue';
 import NavbarComponent from '@/components/NavbarComponent.vue';
 import CardComponent from '@/components/CardComponent.vue';
 import ButtonComponent from '@/components/ButtonComponent.vue';

 const data = ref([])
 onMounted(async () => {
  const response  = await fetch("https://fake-coffee-api.vercel.app/api")
   data.value = await response.json()
 })
 const price = ref(10)

 const result = computed(() => {
    return data.value.filter((item) => item.price < price.value)
 })

 const dec = () => {
   if(price.value > 10){
     price.value--
   }
 }
</script>


<template>
  <div>
    <NavbarComponent />
    <main>
      <div class="border-b-2 border-gray-200 border-solid mb-5">
        <h1 class="my-10 mx-5 text-[50px] coll-head">BEST ELLA ROASTED COFFEE</h1>
      </div>
      <div class="flex px-5">
        <div class="w-[200px] h-full  mr-5">
            <div class="p-3 border-2 border-black border-solid flex mr-3">
              <p class="mr-3">Price:</p>
              <div class="flex">
                <p @click="dec">-</p>
                <p class="mx-5">{{price}}</p>
                <p @click="price++">+</p>
              </div>
            </div>
        </div>
        <div class="grid grid-cols-4 gap-4">
          <div
            class=" bg-slate-400"
            v-for="coffee in result"
            :key="coffee.image"
          >
            <CardComponent :image="coffee.image_url" />
            <ButtonComponent color="primary" style="width: 100%; border: 1px solid black">Add To Cart: {{ coffee.price }}</ButtonComponent>
          </div>

      </div>
      </div>
    </main>
  </div>
</template>

<style>
.coll-head{
  font-style: italic;
  font-weight: 400;
  font-family: 'Amiri', sans;
  color: #00312d;
}
</style>
