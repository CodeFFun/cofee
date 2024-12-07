<script setup lang="js">
    defineProps(['color'])
</script>

<template>
    <button :class="`button button-${color}`" @click="console.log('Pressed')">
        <slot></slot>
    </button>
</template>

<style>
    .button{
        height: 55px;
        min-width: 295px;
        display:flex;
        justify-content: center;
        align-items: center;
        outline: none;
        border: none;
    }

    .button:hover{
        cursor:pointer ;
        font-family: 'DM Sans', sans-serif;
    }

    .button-primary{
        transition: all 1s;
        background-color: #00312d;
        color: #ffffff;
    }
    .button-primary:hover{
        transition: all 1s;
        background-color: #ffffff;
        color: #000000;
    }

    .button-secondary{
        transition: all 1s;
        background-color: #ffffff;
        color: #000000;
    }
    .button-secondary:hover{
        transition: all 1s;
        background-color: #00312d;
        color: #ffffff;
    }
</style>