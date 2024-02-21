<script>
export default {
  name: 'CustomersSection',
  data() {
    return {
      customers: [
        {
          id: 1,
          name: 'Adam',
          quote: 'Autocar made my car buying experience absolutely amazing!',
          image: 'src/assets/Customer/man1.png', 
        },
        {
          id: 2,
          name: 'Carla',
          quote: 'Great selection and customer service. Highly recommend!',
          image: 'src/assets/Customer/testimonial2-1.png',
        },
        {
          id: 3,
          name: 'Frank',
          quote: 'Autocar made my car buying experience absolutely amazing!',
          image: 'src/assets/Customer/man2.png', 
        },
        {
          id: 4,
          name: 'Jane',
          quote: 'Great selection and customer service. Highly recommend!',
          image: 'src/assets/Customer/testimonial4-1.png',
        },

      ],
    };
  },
};
</script>

<template>
    <section class="customer-testimonials my-12 px-4 w-full">
    <div class="container mx-auto">
    
      <h2 class="text-center text-4xl font-bold pt-8 text-white">What Are Our Customers Saying?</h2>
      <h3 class="text-center font-semibold py-11 text-white">Opinions from our happy customers.</h3>
      <div class="flex flex-wrap justify-center items-center gap-6">
        <!-- Card Testimonianze -->
        <div v-for="customer in customers" :key="customer.id" class="testimonial-card w-full md:w-1/5 bg-white rounded shadow-lg p-4 py-8">
          <div class="testimonial-content flex flex-col items-center h-full justify-between">
              <blockquote class="italic text-center m-6">"{{ customer.quote }}"</blockquote>
              <img :src="customer.image" :alt="customer.name" class="w-32 h-32 rounded-full mb-4">
              <p class="text-center font-semibold">{{ customer.name }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
  
</template>

<style scoped>
 .customer-testimonials{
    background-image: url('src/assets/comment-bg-autocar.jpg');
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
    height: 600px;
 }
</style>
