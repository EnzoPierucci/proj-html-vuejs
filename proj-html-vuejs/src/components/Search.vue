

<template>
  <!-- Barra di ricerca -->
  <section class="search-bar my-6 px-4">
    <div class="max-w-screen-lg mx-auto flex flex-wrap items-center space-y-4 md:space-y-0 md:space-x-6 bg-white shadow-lg rounded-lg p-4">
      <input type="text" placeholder="Keywords" class="form-input w-full md:flex-1 rounded-md border-2 border-gray-300 px-8 py-6" v-model="searchQuery" />
      
      <select v-model="selectedLocation" class="form-select w-full md:flex-1 rounded-md border-2 border-gray-300 px-10 py-4">
        <option value="">All Locations</option>
        <option v-for="location in locations" :key="location" :value="location">{{ location }}</option>
      </select>
      
      <select v-model="selectedCategory" class="form-select w-full md:flex-1 rounded-md border-2 border-gray-300 p-6">
        <option value="">All Categories</option>
        <option v-for="category in categories" :key="category" :value="category">{{ category }}</option>
      </select>
      
      <select v-model="selectedBrand" class="form-select w-full md:flex-1 rounded-md border-2 border-gray-300 p-6">
        <option value="">All Brands</option>
        <option v-for="brand in brands" :key="brand" :value="brand">{{ brand }}</option>
      </select>
      
      <select v-model="selectedFuelType" class="form-select w-full md:flex-1 rounded-md border-2 border-gray-300 p-6">
        <option value="">All Fuel Types</option>
        <option v-for="fuelType in fuelTypes" :key="fuelType" :value="fuelType">{{ fuelType }}</option>
      </select>
      
      <select v-model="selectedTransmission" class="form-select w-full md:flex-1 rounded-md border-2 border-gray-300 p-6">
        <option value="">Transmission</option>
        <option v-for="transmission in transmissions" :key="transmission" :value="transmission">{{ transmission }}</option>
      </select>
      
      <button @click="performSearch" class="btn w-full md:w-auto bg-black text-white  p-6">Search</button>
    </div>
  </section>

  
</template>

<style scoped>
 
</style>

<script>
export default {
  name: 'Main',
  data() {
    return {
      searchQuery: '',
      selectedLocation: '',
      selectedCategory: '',
      selectedBrand: '',
      selectedFuelType: '',
      selectedTransmission: '',
      locations: ['Roma', 'Parigi', 'Berlino'],
      categories: ['Cabrio', 'Coupe', 'Hatchback','Pick Up','Sedan','Suv'],
      brands: ['BMW', 'Audi', 'Mercedes','Seat','Volswagen'],
      fuelTypes: ['Petrol', 'Diesel', 'Electric'],
      transmissions: ['Manual', 'Automatic'],
    };
  },
  methods: {
    performSearch() {
      console.log('Search criteria:', {
        query: this.searchQuery,
        location: this.selectedLocation,
        category: this.selectedCategory,
        brand: this.selectedBrand,
        fuelType: this.selectedFuelType,
        transmission: this.selectedTransmission,
      });
    },
  },
};
</script>