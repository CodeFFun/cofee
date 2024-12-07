<script setup>
import SwapComponent from './SwapComponent.vue';
import { ref } from 'vue';

const swap = [
    {
        id: 1,
        background:'/slideshow-5.png',
        heading: 'PINNACLE INSTANT COFFEE REINVENTED',
        desc: 'Each batch is roasted to highlight the unique characteristics of the beans, making every cup a true delight.',
        icon:'/slideshow-dot-4.png'
    },
    {
        id: 2,
        background:'/slideshow-6.png',
        heading: 'THE INTOXICATING TASTE OF LATTE',
        desc: 'Each coffee bean is mixed at standard temperature and after professional processing, quality coffee beans are produced.',
        icon:'/slideshow-dot-2.png'
    },
    {
        id: 3,
        background:'/slideshow-7.png',
        heading: 'MORE THAN JUST COFFEE? iT IS A ART',
        desc: 'Standard flavor from Brazilian mountain coffee. The most outstanding thing is the density of the seeds and the bitter aroma.',
        icon:'/slideshow-dot-3.png'
    },
]


const whichSlide = ref(0)

</script>

<template>
    <SwapComponent  :swap="swap[whichSlide]" @one="(number) => whichSlide = number"/>
</template>

<style>
</style>
