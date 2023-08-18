<template>
  <div>
    <h2 class="weather-wrapper"></h2>
    <ContentHeader />
    <CitySelector @selectCity="selectCity" />
    <WeatherList :weatherList="weatherList" />
  </div>
</template>

<script>
import CitySelector from "./CitySelector.vue";
import ContentHeader from "./ContentHeader.vue";
import WeatherList from "./WeatherList.vue";
import weatherMixin from "@/mixins/weatherMixin";
export default {
  name: "weatherContent",
  components: { ContentHeader, CitySelector, WeatherList },
  data() {
    return {
      weatherList: [],
    };
  },
  mixins: [weatherMixin],
  methods: {
    async selectCity(city) {
      if (city.selected) {
        const weather = await this.getWeatherInfo(city);
        this.weatherList.push(weather);
      } else {
        const index = this.weatherList.findIndex(
          (weather) => weather.code === city.code
        );
        this.weatherList.splice(index, 1);
      }
      console.log(city, "parent received");
    },
  },
};
</script>

<style></style>
