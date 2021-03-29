<template>
  <div class="grid grid-cols-3">
    <div class="m-10 bg-gray-300 rounded-lg col-span-4 sm:col-span-3 md:col-span-2 lg:col-span-1 content-center">
      <input
        class="p-1 m-3 rounded-sm text-gray-700"
        type="text"
        id="cityName"
        placeholder="Nome da cidade..."
        v-model="cityName"
        @keyup.enter="search"
      />
      <input
        class="bg-indigo-500 p-1 m-3 rounded-md text-white uppercase font-bold"
        type="submit"
        value="Buscar"
        @click="search"
      />
    </div>
  </div>
  <Weather :name="infos.name" :description="infos.weather[0].description" :temp="Math.round(infos.main.temp)" :icon="infos.weather[0].icon" :wind="infos.wind.speed" :humidity="(infos.main.humidity)" :visibility="infos.visibility" v-if="infos != null"/>

</template>

<script>
import axios from 'axios';
import { currentKey } from '../assets/keys'
import Weather from './Weather.vue'
export default {
  data() {
    return {
      cityName: '',
      infos: null
    }
  },
  components: {
    Weather
  },
  methods: {
    search(city) {
        city = this.cityName
        axios.get(`http://api.openweathermap.org/data/2.5/weather?q=${city}&appid=${currentKey}&units=metric`)
              .then((response) => { this.infos = response.data })
              .then(console.log(this.infos))
    }
  }
};
</script>

<style>
</style>