

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

  <!-- Disponibili per tipo  -->
  <section class="vehicle-types-indicators my-6 px-4">
    <div class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-6 gap-4">
      <div v-for="info in vehicleTypesInfo" :key="info.type" class="bg-white shadow rounded-lg p-4 flex flex-col items-center justify-center">
        <img :src="info.image" :alt="info.type" class="w-20 h-20 mb-2">
        <h3 class="text-lg font-semibold">{{ info.type }}</h3>
      </div>
    </div>
  </section>

  

<!-- Grid ricerca  -->
  <section class="search-results my-6 px-4">
    <div class="max-w-screen-lg mx-auto grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-4">
      <div v-for="vehicle in filteredVehicles" :key="vehicle.id" class="bg-white shadow rounded-lg overflow-hidden">
        <img :src="vehicle.image" :alt="vehicle.model" class="w-full h-48 object-cover">
        <div class="p-4">
          <h3 class="text-lg font-bold">{{ vehicle.brand }} {{ vehicle.model }}</h3>
          <p>Location: {{ vehicle.location }}</p>
          <p>Type: {{ vehicle.type }}</p>
          <p>Fuel: {{ vehicle.fuelType }}</p>
          <p>Transmission: {{ vehicle.transmission }}</p>
          <p>Price: {{ vehicle.price }}</p>
        </div>
      </div>
    </div>
  </section>

  <!-- Show All Cars  -->
  <section class="flex justify-center my-8">
    <button @click="showAllCars" class="bg-black text-white px-4 py-2 rounded hover:bg-gray-700 transition-colors">
      Show All Cars
    </button>
  </section>

</template>

<style scoped>
 
</style>

<script>
import { vehicles } from '../data/vehiclesData.js';

export default {
  name: 'Main',
  data() {
    return {
      allVehicles: vehicles,
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
      vehicleTypesInfo: [
      { type: 'Sedan', image: 'scr/assets/Show/cabrio.jpg' },
      { type: 'Coupe', image: './assets/Show/cabrio.jpg' },
      { type: 'Hatchback', image: './assets/Show/cabrio.jpg' },
      { type: 'Pick Up', image: './assets/Show/cabrio.jpg' },
      { type: 'Sedan', image: './assets/Show/cabrio.jpg' },
      { type: 'SUV', image: './assets/Show/cabrio.jpg' },   
     ],
    };
  },
  computed: {
  filteredVehicles() {
    return this.allVehicles.filter((vehicle) => {
      return (
        (this.searchQuery.length === 0 || vehicle.model.toLowerCase().includes(this.searchQuery.toLowerCase())) &&
        (this.selectedLocation === '' || vehicle.location === this.selectedLocation) &&
        (this.selectedCategory === '' || vehicle.type === this.selectedCategory) &&
        (this.selectedBrand === '' || vehicle.brand === this.selectedBrand) &&
        (this.selectedFuelType === '' || vehicle.fuelType === this.selectedFuelType) &&
        (this.selectedTransmission === '' || vehicle.transmission === this.selectedTransmission)
      );
    });
  }
  },

  //Logica per Show All Cars 
  methods: {
    showAllCars() {
      this.searchQuery = '';
      this.selectedLocation = '';
      this.selectedCategory = '';
      this.selectedBrand = '';
      this.selectedFuelType = '';
      this.selectedTransmission = '';
    },
  },
}  
</script>