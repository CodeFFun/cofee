<script setup>
    import ButtonComponent from './ButtonComponent.vue';

</script>

<template>
    <section class="banner">
        <div class="hero-content">
          <h1>BEST ESPRESSO<br/>EXPERIENCE</h1>
            <p>Explore Our Enchanted Collection: Deep Dark Coffee Bean Season</p>
            <div class="hero-btn-group">
                <ButtonComponent color="secondary">Shop Now</ButtonComponent>
                <ButtonComponent color="primary">Discover Recipies</ButtonComponent>
            </div>
        </div>

    </section>
</template>

<style>
    .banner {
    min-height: 95vh;
    background: url('/slideshow-8.png') ;
    background-repeat: no-repeat;
    background-size: cover;
    display: flex;
    align-items: center;

}

.banner-content {
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    align-items: flex-start;
    color: #ffffff;
    padding: 25px 30px;
    margin: 40px 0;
}
.hero-content h1 {
    font-size: 70px;
    line-height: 77px;
    font-style: italic;
    font-family: 'Amiri', serif;
    overflow: hidden;
    padding: 5px;
}

.hero-content p{
    margin: 25px 0 50px 0
}

.hero-btn-group{
    display: flex;
    gap: 10px;
}

</style>
