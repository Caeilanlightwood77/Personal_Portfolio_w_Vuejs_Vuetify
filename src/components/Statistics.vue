<script>
export default {
  name: "StatsSection",
};
</script>

<template>
  <v-container id="stats" class="accent-background pa-10" fluid>

    <v-container
      class="position-relative"
      data-aos="fade-up"
      data-aos-delay="100"
    >
      <v-row dense class="text-center">
        <!-- Clients -->
        <v-col cols="12" md="3" sm="6">
          <v-card class="stats-item py-5">
            <div class="stat-number display-1 font-weight-bold">0</div>
            <p>Clients</p>
          </v-card>
        </v-col>

        <!-- Projects -->
        <v-col cols="12" md="3" sm="6">
          <v-card class="stats-item py-5">
            <div class="stat-number display-1 font-weight-bold">3</div>
            <p>Projects</p>
          </v-card>
        </v-col>

        <!-- Hours Of Support -->
        <v-col cols="12" md="3" sm="6">
          <v-card class="stats-item py-5">
            <div class="stat-number display-1 font-weight-bold">0</div>
            <p>Hours Of Support</p>
          </v-card>
        </v-col>

        <!-- Awards -->
        <v-col cols="12" md="3" sm="6">
          <v-card class="stats-item py-5">
            <div class="stat-number display-1 font-weight-bold">1</div>
            <p>Awards</p>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </v-container>
</template>

<style scoped>
.accent-background {
  background-color: #0077FF; /* Adjust background color as needed */
  padding: 40px 0;
}

.stats-background {
  position: absolute;
  top: 0;
  left: 0;
  height: 100%;
  width: 100%;
  z-index: -1;
  opacity: 0.4; /* Background image transparency */
}

.stats-item {
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  background-color: white; /* Adjust card background color */
  border-radius: 8px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

.stat-number {
  color: #333;
}
</style>
