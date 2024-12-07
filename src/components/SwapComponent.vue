<script setup>
import ButtonComponent from './ButtonComponent.vue';
defineProps({
  swap: {
    type: Object,
    required: true
  }
});

defineEmits(['one']);

</script>

<template>
    <section class="swap-section"
    :style="{ background: `url(${swap.background})` }">
        <div class="swap-desc">
            <h1>{{ swap.heading }}</h1>
            <p>{{ swap.desc }}</p>
            <ButtonComponent color="secondary">Shop Now</ButtonComponent>
        </div>
        <div class="swap-icon">
            <div>
                <div v-if="swap.id == 1">
                    <img :src="swap.icon" alt="icon">
                </div>
                <div v-else style="border-radius: 50%; background-color: grey;" @click="$emit('one', 0)">+</div>
            </div>
            <div>
                <div v-if="swap.id == 2"><img :src="swap.icon" alt="icon"></div>
                <div v-else style="border-radius: 50%; background-color: grey;" @click="$emit('one', 1)">+</div>
            </div>
            <div>
                <div v-if="swap.id == 3"><img :src="swap.icon" alt="icon"></div>
                <div v-else style="border-radius: 50%; background-color: grey;" @click="$emit('one', 2)">+</div>
            </div>
        </div>
    </section>
</template>

<style>
    .swap-section{
    min-height: 100vh;
    max-width: 100vw;
    background-repeat: no-repeat;
    background-size: cover;
    display: flex;
    align-items: center;
    justify-content: space-around;
    }

    .swap-desc{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: flex-start;
    color: #ffffff;
    padding: 25px 0px;
    margin: 40px 0;
    }

    .swap-desc h1 {
    font-size: 70px;
    line-height: 77px;
    width: 50%;
    font-style: italic;
    font-family: 'Amiri', serif;
    overflow: hidden;
    padding: 5px;
    }

    .swap-desc p{
        width: 50%;
        margin: 25px 0 50px 0;
    }

    .swap-icon{
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    max-width: fit-content;
    overflow: hidden;
    gap: 20px;
    }

    .swap-icon div{
    width: 80px;
    height: 80px;
    overflow: hidden;
    display: flex;
    justify-content: center;
    align-items: center;
    color: #ffffff;
    }


</style>
