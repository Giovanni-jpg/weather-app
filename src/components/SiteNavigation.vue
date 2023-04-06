<template>
  <header class="sticky top-0 bg-weather-primary shadow-lg">
    <nav
      class="container flex flex-col sm:flex-row itmes-center gap-4 text-white py-6"
    >
      <RouterLink :to="{ name: 'home' }">
        <div class="flex items-center gap-3">
          <i class="fa-solid fa-sun text-2xl"></i>
          <p class="text-2xl">Sunny Weather App</p>
        </div>
      </RouterLink>

      <div class="flex gap-3 flex-1 justify-end">
        <i
          @click="toggleModal"
          class="fa-solid fa-circle-info text-xl hover:text-weather-secondary duration-150 cursor-pointer"
        ></i>
        <i
          class="fa-solid fa-plus text-xl hover:text-weather-secondary duration-150 cursor-pointer"
        ></i>
      </div>

      <BaseModal :modalActive="modalActive" @close-modal="toggleModal">
        <div class="text-black">
          <h1 class="text-2xl mb-1">About:</h1>
          <p class="mb-4">
            Sunny weather app is a simple weather app that allows you to search
            for a city and track its current weather
          </p>
          <h2 class="text-2xl">How to use it:</h2>
          <ol class="list-decimal list-inside mb-4">
            <li>
              First use the bar at the top of the page to search for a city.
            </li>
            <li>
              Within the results, pick the city you wish to see: this is taking
              you to the weather page of this city
            </li>
            <li>
              If you want to track the city, just click on the '+' icon at the
              top right of the page. This will add it to your home page.
            </li>
          </ol>

          <h2 class="text-2xl">To remove a city</h2>
          <p>
            Select the city in the list and use the delete option you can find
            at the bottom of your screen.
          </p>
        </div>
      </BaseModal>
    </nav>
  </header>
</template>

<script setup>
import { ref } from 'vue';
import { RouterLink } from 'vue-router';
import BaseModal from './BaseModal.vue';

const modalActive = ref(null);
const toggleModal = () => {
  modalActive.value = !modalActive.value;
};
</script>
