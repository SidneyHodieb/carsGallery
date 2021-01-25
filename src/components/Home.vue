<template>
  <div>

    <!-- NavBar start -->
    <v-app-bar
      id="home-app-bar"
      app
      color="white"
      elevation="1"
      height="80"
    >

      <v-img
        src="https://ophelia-sensors.com/web/image/res.company/1/logo?unique=27bd28e"
        class="mr-3 hidden-xs-only"
        contain
        max-width="150"
        width="100%"
      ></v-img>



      <v-spacer />

      <div>
        <v-tabs
          class="hidden-sm-and-down"
          optional
        >

        </v-tabs>
      </div>

      <v-app-bar-nav-icon
        class="hidden-md-and-up"
        @click="drawer = !drawer"
      />
    </v-app-bar>

      <!-- NavBar End -->

    <section id="hero">
    <v-img

      src="https://i.gaw.to/content/photos/40/55/405566_Sony_surprend_au_CES_2020_en_devoilant_une_voiture.jpg"
      class="white--text"
      gradient="to right, rgba(5, 11, 31, .8), rgba(5, 11, 31, .8)"
    >
      <v-container class="fill-height px-4 py-12">
        <v-responsive
          class="d-flex align-center"
          height="100%"
          max-width="600"
          width="100%"
        >
          <h1 class="text-center font-weight-bold">
           Bienvenue Sur Ophelia Sensors
          </h1>

        </v-responsive>
      </v-container>
    </v-img>
  </section>



  <h2 style="margin : 20px; margin-bottom : 20px" class="text-center font-weight-bold">Voitures par classes </h2>

  <!-- Body of th page which come from the Body.vue file -->
      <pageBody/>

      <!-- End Body -->

  </div>
</template>

<script>
import pageBody from './Body'
  export default {
    name: 'Home',
    components :{
      pageBody
    },
    computed: {

    }
  }
</script>

<style lang="sass">
  #home-app-bar
    .v-tabs-slider
      max-width: 24px
      margin: 0 auto

    .v-tab
      &::before
        display: none
</style>
