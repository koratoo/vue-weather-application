<template>
  <div>
    <HeaderDisplay />
    <WeatherContent />
  </div>
</template>

<script>
import WeatherContent from "./components/weather/WeatherContent";
import HeaderDisplay from "./components/HeaderDisplay";
export default {
  name: "App",
  components: { HeaderDisplay, WeatherContent },
};
</script>

<style></style>
