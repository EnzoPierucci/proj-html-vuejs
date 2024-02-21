<script>
import SliderComp from '../components/Slider.vue'
import SearchComp from '../components/Search.vue'
export default {
  name: 'App',
  components: {
    SliderComp,
    SearchComp,
    
  }
};
</script>

<template>
  <SliderComp class=""/>
  <SearchComp/>

    <!-- Sezione "Want to buy or sell a vehicle?" -->
  <section class="my-12 px-4 bg-gray-100 py-10">
    <div class="container mx-auto flex flex-wrap items-center justify-between">
      <!-- Immagine a sinistra -->
      <div class="w-full md:w-1/2">
        <img src="../assets/aoutcar-about-1.png" alt="Car" class="block mx-auto md:mx-0 md:mr-8" />
      </div>

      <!-- Info destra -->
      <div class="w-full md:w-1/2 mt-6 md:mt-0">
        <h2 class="text-3xl font-bold mb-4">Want to buy or sell a vehicle?</h2>
        <p class="mb-4">
          You can put your vehicles for sale by registering on our website. Whether you are a dealer or sell personally, sell your vehicle in the most profitable way. With this system, which has millions of members, you will be able to buy and sell vehicles quickly.
        </p>
        <div class="mb-4">
          <div>
            <h3 class="text-xl font-semibold">Model Vehicles</h3>
            <p>Discover a wide range of new models on our site.</p>
          </div>
          <div class="mt-4">
            <h3 class="text-xl font-semibold">2nd Hand Vehicles</h3>
            <p>Explore our collection of pre-owned vehicles.</p>
          </div>
        </div>
        <button class="bg-black text-white px-6 py-2 rounded hover:bg-gray-700 transition-colors">
          Get to know us
        </button>
      </div>
    </div>
  </section>   
</template>

<style scoped>
 
</style>
