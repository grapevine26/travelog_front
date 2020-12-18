<template>
  <div class="justify-center align-center">
    <div id="main_i" class="main_img text-center" >
      <div class="main_logo">Leo & Heidi's travel diary in Korea</div>
      <v-btn style="margin: 20px 0;" text outlined large @click="$vuetify.goTo(target, options)">
        GET MORE INFO
      </v-btn>
    </div>
    <div class="photo_list">
      <div class="main_logo">Leo & Heidi's travel diary in Korea</div>
      <v-btn id="vb" style="margin: 20px 0;" text outlined large to="/whoarewe">GET MORE INFO</v-btn>
    </div>
  </div>
</template>

<script>
  import * as easings from 'vuetify/es5/services/goto/easing-patterns'

  export default {
    data() {
      return {
        menuValue: null,
        target: '#vb',
        options: {
          duration: 1000,
          offset: 0,
          easing: 'easeInOutQuint',
        },
        easings: Object.keys(easings),
      }
    },
  }
</script>

<style scoped>
  /*@import url('https://fonts.googleapis.com/css2?family=Crimson+Text:ital,wght@1,700&display=swap')*/

  .main_img {
    width: 100%;
    height: 93.2vh;
    max-width: 100%;
    text-align: center;
    background-image: url('~assets/img/mainphoto.jpg');
    background-position: center;
    background-size: cover;
    background-repeat: no-repeat;
  }

  .main_logo {
    font-family: 'Crimson Text', serif;
    font-weight: 700;
    font-size: 4vw;
    padding-top: 26vh;
    color: #507080;
  }

  @media (max-width: 960px) {
    .main_logo {
      font-size: 9vw;
      margin-top: 21vh;
    }
  }

  .v-btn.active .v-icon {
    transform: rotate(-180deg);
  }
</style>
