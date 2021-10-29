<template>
  <v-row>
    <v-col class="align-center" cols="6">
      <h1>Hotel Name</h1>
      <h3 class="mt-2">Desc</h3>
      <v-row class="mt-2">
        <v-col class="d-flex align-center">
          <div>
            <v-icon>
              mdi-map-marker
            </v-icon>
            Hotel Location
          </div>
        </v-col>
        <v-col>
          <v-dialog
            ref="dialog"
            v-model="modal"
            :return-value.sync="date"
            persistent
            width="290px"
          >
            <template v-slot:activator="{ on, attrs }">
              <v-text-field
                v-model="dateRangeText"
                label="Reservation Dates"
                prepend-icon="mdi-calendar"
                readonly
                v-bind="attrs"
                v-on="on"
              ></v-text-field>
            </template>
            <v-date-picker
              v-model="dates"
              range
              scrollable
              :min="new Date().toISOString().substr(0, 10)"
            >
              <v-spacer></v-spacer>
              <v-btn text color="primary" @click="modal = false">
                Cancel
              </v-btn>
              <v-btn text color="primary" @click="$refs.dialog.save(date)">
                OK
              </v-btn>
            </v-date-picker>
          </v-dialog>
        </v-col>
      </v-row>
    </v-col>
    <v-col cols="6" class="d-flex align-center">
      <v-img height="500px" width="500px" contain src="@/assets/logo.svg" />
    </v-col>
  </v-row>
</template>

<script>
export default {
  data() {
    return {
      dates: [],
      modal: false,
      date: new Date(Date.now() - new Date().getTimezoneOffset() * 60000)
        .toISOString()
        .substr(0, 10)
    };
  },
  computed: {
    dateRangeText() {
      return this.dates.join(" - ");
    }
  }
};
</script>

<style>
</style>