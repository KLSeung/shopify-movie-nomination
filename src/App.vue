<template>
  <v-app>
    <v-app-bar color="#43a047" dark app>
      <!-- <div class="d-flex align-center">
        <h2>The Shoppies</h2>
      </div> -->
      <v-app-bar-title
        @click="$router.push('/')"
        class="app-bar-title ml-13"
      >
        The Shoppies
      </v-app-bar-title>
      <v-spacer></v-spacer>
    </v-app-bar>

    <v-main>
      <SearchMovieBar/>
      <v-row
        :class="{'mx-5': $vuetify.breakpoint.xs, 'mx-16': $vuetify.breakpoint.smAndUp }"
        dense
      >
        <v-col class="ma-0 pa-0" :class="{'pr-12': $vuetify.breakpoint.mdAndUp }" :cols="cols">
          <SearchMovieResults/>
        </v-col>
        <v-col class="ma-0 pa-0" :cols="cols">
          <NominatedMovies/>
        </v-col>
      </v-row>
    </v-main>
  </v-app>
</template>

<script>
import SearchMovieBar from './components/SearchMovieBar.vue'
import SearchMovieResults from './components/SearchMovieResults.vue'
import NominatedMovies from './components/NominatedMovies.vue'

export default {
  name: 'App',

  components: {
    SearchMovieBar,
    SearchMovieResults,
    NominatedMovies,
  },

  computed: {
    cols() {
      if (this.$vuetify.breakpoint.width <= 768) {
        return 12
      }
      return 6
    },
  },
}
</script>

<style lang="scss" scoped>
  .app-bar-title {
    cursor: pointer;
  }
</style>
