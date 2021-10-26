<template>
  <v-app>
    <v-app-bar app color="#d3eaed" dark>
      <div class="d-flex align-center">
        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="./assets/hotel.svg"
          transition="scale-transition"
          width="40"
        />
        <v-btn href="#" text style="font-size: 32px">Hotels</v-btn>
      </div>

      <v-spacer></v-spacer>

      <div>
      <v-autocomplete
        label="Country"
        color="primary"
        cache-items
        :search-input.sync="search"
        hide-details
        hide-no-data
      >
      </v-autocomplete>
      </div>
    </v-app-bar>

    <v-main>
      <v-row no-gutters>
        <v-col cols="6" v-for="n in 12" :key="n">
          <MainPage/>
        </v-col>
      </v-row>
      <!-- <MainPage /> -->
    </v-main>
  </v-app>
</template>

<script>
import MainPage from "./components/MainPage";

export default {
  name: "App",

  components: {
    MainPage
  },

  data: () => ({
    data: null
  })
};
</script>

<style >
.v-select.v-text-field input {
  color: #800000 !important;
  font-size:16px;
}
.v-select.v-text-field label {
  color: #800000 !important;
}
.v-select {
  color: #800000;
}
</style> 