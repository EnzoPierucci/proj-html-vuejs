<script>
import SliderComp from '../components/Slider.vue'
import SearchComp from '../components/Search.vue'
import CustomersComp from '../components/Customers.vue'
import RecentArticlesComp from '../components/RecentArticles.vue'

export default {
  name: 'App',
  components: {
    SliderComp,
    SearchComp,
    CustomersComp,
    RecentArticlesComp,

  }
};
</script>

<template>
  <SliderComp/>
  <SearchComp/>

    <!-- Sezione "Want to buy or sell a vehicle?" -->
  <section class="my-12 px-4 bg-gray-100 py-10">
    <div class="container mx-auto flex gap-4 items-center justify-between">
      <!-- Immagine a sinistra -->
      <div class="w-full md:w-1/2 relative mask">
        <img src="../assets/aoutcar-about-1.png" alt="Car" class="block mx-auto md:mx-0 md:mr-8 object-cover w-full h-full" />
        <div class="absolute top-0 left-0 right-0 bottom-0 flex justify-between items-center">
          <!-- Cerchio 1  -->
          <div class="rounded-full bg-black w-40 h-40 flex flex-col items-center justify-center text-white absolute top-0 left-0">
            <span class="font-bold">24</span>
            <span class="font-bold">years of</span>
            <span class="font-bold">experience</span>          
          </div>
          <!-- Cerchio 2  -->
          <div class="rounded-full bg-black w-40 h-40 flex flex-col items-center justify-center text-white absolute bottom-10 right-14">
            <span class="font-bold">240</span>
            <span class="font-bold">Special Expert</span>
            <span class="font-bold">Team</span>
          </div>
        </div>
      </div>
      <!-- Info destra -->
      <div class="w-full md:w-1/2 mt-6 md:mt-0 ml-9">
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
  
  <CustomersComp/>
  <RecentArticlesComp/>
  

</template>

<style scoped>
 .mask{
  background-image: url("../assets/circle-auto-car-1.png");
  background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
    height: 700px;

 }
</style>
