<template>
  <div class="about">
    <h1>This is an about page</h1>
  </div>
</template>

<script>
  export default {
    data() {
      return {}
    },
  }
</script>

<style>
  .row {
    margin: 0;
  }

  .index_img {
    background-image: url('~assets/img/mainphoto.jpg');
    background-position: center;
    background-size: cover;
    background-repeat: no-repeat;
    max-width: 100%;
    width: 100%;
    height: 100%;
    padding: 0;
    margin: 0;
  }

  .content_logo {
    width: 50%;
  }

  @media (max-width: 960px) {
    .content_logo {
      width: 100%;
    }
  }
</style>
