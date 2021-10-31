<template>
  <div>
    <v-row>
      <v-col v-for="i in guestCount" :key="i" cols="6">
        <v-card>
          <v-card-title class="justify-center"> Reservation Form </v-card-title>
          <v-card-text>
            It's me mario
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  data() {
    return {
      guestCount: Number,
      dates: []
    };
  },
  mounted: function() {
    this.guestCount = this.$route.params.guestCount;
    this.dates = this.$route.params.dates;
  }
};
</script>

<style>
</style>