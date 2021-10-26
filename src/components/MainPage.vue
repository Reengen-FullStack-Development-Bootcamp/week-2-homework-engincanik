<template>
  <v-container class="pt-6">
    <v-row class="justify-center">
      <span>Main Page</span>
    </v-row>
    <v-card @click="goToDetails('id')" id="card" max-width="500" class="mx-auto my-12">
      <v-img height="250" src="../assets/logo.svg"></v-img>
      <v-card-title>Hotel Name</v-card-title>
      <v-card-text>
        <v-row align="center" class="mx-0">
          <v-rating
            :value="4.5"
            color="amber"
            dense
            half-increments
            readonly
            size="14"
          ></v-rating>
          <div class="grey--text ms-4">4.5(413)</div>
        </v-row>
        <div class="my-4 text-subtitle-1">$ Price • Country</div>
        <div>
          The Jianguo Hotel Qianmen is located near Tiantan Park, just a
          10-minute walk from the National Center for the Performing Arts and
          Tian'anmen Square. Built in 1956 it has old school charm and many
          rooms still feature high, crown-molded ceilings.
        </div>
      </v-card-text>
      <!-- <v-divider class="mx-4"></v-divider> -->
      <!-- <v-card-text>
        <v-row class="d-flex justify-space-between">
          <div class="ms-4 text-subtitle-1 blue--text d-flex align-center">
            Guest amount:
          </div>
          <div class="d-flex align-center">
            <v-btn class="mx-2" fab dark x-small color="#333333">
              <v-icon dark>
                mdi-minus
              </v-icon>
            </v-btn>
            <v-card-text class="black--text">5</v-card-text>
            <v-btn class="mx-2" fab dark x-small color="#333333">
              <v-icon dark>
                mdi-plus
              </v-icon>
            </v-btn>
          </div>
        </v-row>
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
      </v-card-text> -->
    </v-card>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      peopleCount: 0,
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
  },
  methods: {
    goToDetails(id) {
      console.log(id)
      window.location = '#'
    }
  }
};
</script>

<style #scoped>
#card {
  border-style: solid;
  border-color: #333333;
}
</style>