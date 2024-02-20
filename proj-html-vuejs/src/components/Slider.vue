<script>
export default {
  name: 'Slider',
  data() {
    return {
      currentIndex: 0,
      images: [
        { src: 'src/assets/Slider/slider-autocar-5.jpg', alt: '1', text1:'Buy And Sell Your', text2: 'Car At Its Value', text3:'Find the rihgt and dealer', button:'Learn More' },
        { src: 'src/assets/Slider/slider-autocar-6.jpg', alt: '2', text1:'Buy And Sell Your', text2: 'Car At Its Value', text3:'Find the rihgt and dealer', button:'Learn More' },
        
        
      ],
    };
  },
  methods: {
    next() {
      this.currentIndex = (this.currentIndex + 1) % this.images.length;
    },
    prev() {
      this.currentIndex = (this.currentIndex - 1 + this.images.length) % this.images.length;
    },
  },
};
</script>

<template>
  <section class="carousel w-full mx-auto overflow-hidden">
    <div class="flex transition-all duration-300 ease-in-out" :style="{ transform: `translateX(-${currentIndex * 100}%)` }">
      <!-- Immagini -->
      <div v-for="(image, index) in images" :key="index" class="flex-shrink-0 w-full">
        <img :src="image.src" :alt="image.alt" :class="'w-full object-cover'">
        <div class="SlidFix">

            <p class="SlidP1 mb-5 font-bold">{{ image.text1 }}</p>
            
            <p class="SlidP1 mb-5 font-bold">{{ image.text2 }}</p>
            
            <p class="SlidP2 mb-5 font-bold">{{ image.text3 }}</p>
            
            <button class="px-12 py-5 text-white bg-black">{{ image.button }}</button>
        </div>
      </div>
    </div>

    <!-- Pulsanti di navigazione -->
    <button @click="prev" class="absolute left-0 top-1/2 transform -translate-y-1/2 px-4 py-4 bg-black text-white">
        <span>&lt;</span>
    </button>
    <button @click="next" class="absolute right-0 top-1/2 transform -translate-y-1/2 px-4 py-4 bg-black text-white">
        <span>&gt;</span>
    </button>
  </section>
</template>

<style scoped>
 .SlidFix{
    position: absolute;
    top:200px;
    left:120px;
    color: white;
    padding: 40px;
 }

 .SlidP1 {
    font-size: 50px;
    line-height: 28px;
    font-weight: 600px;
    
 }

 .SlidP2 {
    font-size: 22px;
    line-height: 28px;
    font-weight: 600px;
 }


</style>
