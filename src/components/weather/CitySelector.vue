<template>
  <div>
    <ul class="city-selector">
      <li
        @click="selectCity(city)"
        :class="{ isSelected: city.selected === true }"
        v-for="city in cities"
        :key="city.code"
      >
        {{ city.label }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "CitySelector",
  data() {
    return {
      cities: [
        { code: "Seoul", label: "서울", selected: false },
        { code: "London", label: "런던", selected: false },
        { code: "Toronto", label: "토론토", selected: false },
        { code: "Tokyo", label: "도쿄", selected: false },
        { code: "New York", label: "뉴욕", selected: false },
        { code: "Daegu", label: "대구", selected: false },
        { code: "Shanghai", label: "상하이", selected: false },
        { code: "Beijing", label: "베이징", selected: false },
        { code: "Yakutsk", label: "야크추크", selected: false },
        { code: "Moscow", label: "모스크바", selected: false },
        { code: "Incheon", label: "인천", selected: false },
        { code: "Paris", label: "파리", selected: false },
        { code: "Bucheon", label: "부천", selected: false },
        { code: "Pusan", label: "부산", selected: false },
      ],
    };
  },
  methods: {
    selectCity(city) {
      city.selected = !city.selected;
      this.$emit("selectCity", city);
    },
  },
};
</script>

<style scoped>
.city-selector {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
}

.city-selector li {
  display: flex;
  justify-content: center;
  align-items: center;
  border: 0.05em solid #efefef;
  padding: 0.3em;
  cursor: pointer;
}

.isSelected {
  background: #fd1d1d;
  color: #fff;
}
</style>
