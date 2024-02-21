<script>
export default {
  name: 'RecentArticlesSection',
  data() {
    return {
      articles: [
        {
          id: 1,
          title: 'Why is BMW so loved?',
          summary: 'An insight into what makes BMW a great choice for car enthusiasts.',
          image: 'src/assets/Articles/news-autocar-1.jpg',
        },
        {
          id: 2,
          title: 'Why is BMW so loved?',
          summary: 'An insight into what makes BMW a great choice for car enthusiasts.',
          image: 'src/assets/Articles/news-autocar-1.jpg',
        },
        {
          id: 3,
          title: 'Why is BMW so loved?',
          summary: 'An insight into what makes BMW a great choice for car enthusiasts.',
          image: 'src/assets/Articles/news-autocar-1.jpg',
        },
        {
          id: 4,
          title: 'Why is BMW so loved?',
          summary: 'An insight into what makes BMW a great choice for car enthusiasts.',
          image: 'src/assets/Articles/news-autocar-1.jpg',
        },

      ],
    };
  },
};
</script>

<template>
      
<section class="recent-articles my-12 px-4 bg-gray-100 py-10">
    <div class="container mx-auto">
      <h2 class="text-center text-4xl font-semibold">Recent Articles</h2>
      <h3 class="text-center  mb-10">Useful information about car</h3>
      <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-4 gap-6">
        <!-- Card Articolo -->
        <div v-for="article in articles" :key="article.id" class="article-card rounded-lg overflow-hidden shadow-lg">
          <img :src="article.image" :alt="article.title" class="w-full h-48 object-cover">
          <div class="p-4 justify-center text-center">
            <h3 class="text-xl font-semibold mb-2">{{ article.title }}</h3>
            <p class="text-gray-600 mb-4">{{ article.summary }}</p>
            <button @click="showAllCars" class="bg-black text-white px-4 py-2 rounded hover:bg-gray-700 transition-colors ">
                 More
            </button>
          </div>
        </div>
      </div>
    </div>
</section>
</template>

<style scoped>
 
</style>
