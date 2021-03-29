<template>
  <div class="grid grid-cols-6" id="result">
    <div class="m-10 bg-gray-300 text-gray-900 rounded-lg col-span-5 sm:col-span-4 md:col-span-3 lg:col-span-3">
      <h1 class="text-center font-bold uppercase" id="name">{{ name }}</h1>
      <div class="m-3 place-content-center">
        <img
          :src="'http://openweathermap.org/img/wn/' + icon + '@2x.png'"
          alt=""
        />
        <p class="text-left font-bold uppercase" id="description">
          {{ description }}
        </p>
      </div>
      <div class="">
        <p class="text-right text-6xl md:text-7xl relative" d="temp">
          {{ temp }}º
        </p>
      </div>

      <div class="p-1 grid grid-cols-6 lg:grid-cols-3">
          <div>
            <label for="wind">Vento</label>
            <p id="wind">{{ wind }} m/s</p><br />
          </div>
          <div>
            <label for="humidity">Humidade</label>
            <p id="humidity">{{ humidity }}%</p><br />
          </div>
          <div>
            <label for="visibility">Visibilidade</label>
            <p id="visibility">{{ visibility / 1000 }} km</p>
          </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Result",
  props: [
    "name",
    "description",
    "temp",
    "icon",
    "wind",
    "humidity",
    "visibility",
  ],
};
</script>

<style>
</style>