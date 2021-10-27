<template>
  <v-row no-gutters>
    <v-col cols="6" v-for="n in 12" :key="n">
      <HotelCard :id="n" />
    </v-col>
  </v-row>
</template>


<script>
import HotelCard from "../components/HotelCard.vue"

export default {
  components: {
    HotelCard
  }
};
</script>

<style #scoped>
</style>