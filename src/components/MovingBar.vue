<script setup>
</script>

<template>
    <section class="moving-div">
      <div class="slider">
        <p>Free Shipping over $99</p>
        <p>Secure Checkout Guarantee</p>
        <p>Secure Checkout Guarantee</p>
      </div>
    </section>
  </template>
  
  <style scoped>
  .moving-div {
    width: 100%;
    border-bottom: 2px solid black;
    color: #0B0B0B;
    padding: 20px 0;
  }
  
  .slider {
    display: flex;
    width: 100%;
    justify-content: space-around;
    animation: scroll 10s linear infinite;
  }
  
  .slider p {
    white-space: nowrap; /* Prevent line breaks */
    font-size: 1em;
    font-weight: 700;
  }
  
  @keyframes scroll {
  0% {
    transform: translateX(100%);
  }
  100% {
    transform: translateX(-100%);
  }
}

  </style>
  