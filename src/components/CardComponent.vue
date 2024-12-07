<script setup>

defineProps(['image'])
</script>

<template>
    <div class="card">
        <img :src="image" class="card-image" alt="Coffee Collection"/>
    </div>
</template>

<style>
    .card{
        width: 435px;
        height: 585px;
        overflow: hidden;
    }

    .card-image{
        width: 100%;
        height: 100%;
        object-fit: contain;
        overflow: hidden;
    }
</style>