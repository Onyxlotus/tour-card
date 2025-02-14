<script setup>
import TourCard from './components/TourCard.vue';

const tourData = {
  title: "Crystal Land Of Paradise",
  extitle: "Alonya Beach",
  score: "3,6",
  reviews: "1 276",
  stars: 3,
  distanceToSea: "100 м",
  distanceToAirport: "62 км",
  location: "Турция, Анталья (Antalya), Коньяалты (Konyalti)",
  googleMapsLink: "https://www.google.com/maps?q=Анталия,Коньяалты,Crystal Land Of Paradise",
  price: "от 325 670 ₽",
};
</script>

<template>
  <div class="app">
    <TourCard v-bind="tourData" />
  </div>
</template>

<style>
.app {
  display: flex;
  justify-content: center;
  padding: 20px;
}
</style>