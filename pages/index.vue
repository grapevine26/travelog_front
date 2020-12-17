<template>
  <v-layout justify-center align-center>
    <div style="text-align: center">
      <div class="main_logo">Leo & Heidi's travel diary in Korea</div>
      <v-btn style="margin: 20px 0;" text outlined large to="/whoarewe">GET MORE INFO</v-btn>
    </div>
  </v-layout>
</template>

<script>
  export default {
    data() {
      return {}
    },
  }
</script>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Crimson+Text:ital,wght@1,700&display=swap')

  .v-application {
    background-image: url('~assets/img/mainphoto.jpg') !important;
    max-width: 100%;
    width: 100%;
    height: 100%;
    padding: 0;
    margin: 0;
    background-position: center !important;
    background-size: cover !important;
    background-repeat: no-repeat !important;
  }

  .main_logo {
    font-family: 'Crimson Text', serif;
    font-weight: 700;
    font-size: 4vw;
    margin-top: 25vh;
  }

  @media (max-width: 960px) {
    .main_logo {
      font-size: 9vw;
      margin-top: 21vh;
    }
  }
</style>
