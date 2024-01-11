<script>
  export default {
    data() {
      return {
        meals: ""
      };
    },
    methods: {
      fetchUrl() {
        fetch('https://openmensa.org/api/v2/canteens/63/days/02-02-2023/meals')
            .then((response) => {
              response.json().then((data) => {
                this.meals = data;
              })
            });
      }
    }
  }
</script>

<template>
  <button type="button" @click="fetchUrl">Show meals</button>
  <p>{{ meals }}</p>
</template>

