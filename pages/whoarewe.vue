<template>
  <v-container>
    <v-layout style="height: 100%;">
      <v-card class="background_img index_img" color="rgb(255, 0, 0, 0.2)">

      </v-card>
      <v-row justify="center" align="center">

      </v-row>
    </v-layout>
  </v-container>
</template>

<script>
  export default {
    data() {
      return {}
    },
  }
</script>

<style scoped>
  .background_img {
    background-position: center;
    background-size: cover;
    background-repeat: no-repeat;
  }

  .index_img {
    background-image: url('~assets/img/suroview.jpg');
    max-width: 100%;
    width: 100%;
    height: 50%;
    padding: 0;
    margin: 0;
  }
</style>
