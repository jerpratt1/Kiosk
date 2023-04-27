<template>
  <div class="main">
    <div class="weather" v-if="populated">
      <div id="location">Location: {{ location.name }}</div>
      <div>Current Temp: {{ currentWeather.temp_f }} &#8457;</div>
      <div>Feels Like: {{ currentWeather.feelslike_f }} &#8457;</div>
      <div>Wind Speed: {{ currentWeather.wind_mph }} MPH</div>
    </div>
    <div>
      <button class="button" v-on:click="getCurrentWeather">
        Click Here to get weather
      </button>
    </div>
  </div>
</template>

<script>
import WeatherService from "../services/WeatherService.js";
export default {
  data: function () {
    return {
      currentWeather: {},
      location: {},
      populated: false,
    };
  },

  methods: {
    getCurrentWeather() {
      WeatherService.getCurrentWeather().then((response) => {
        this.currentWeather = response.data.current;
        this.location = response.data.location;
      });
      this.populated = true;
    },
  },
};
</script>

<style scoped>
.button {
  margin-top: 10px;
  background-color: whitesmoke;
  color: black;
  border: 3px solid gray;
  border-radius: 5px;
}

.button:hover {
  background-color: gray;
}

.weather {
  display: flex;
  flex-direction: row;
  justify-content: space-evenly;
  align-items: center;
  border: 3px solid gray;
  padding: 10px;
  
  border-radius: 5px;
}

.main {
  padding-top: 10px;
  padding-right: 10%;
  padding-left: 10%;
}
</style>