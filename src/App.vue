<template>
  <v-app>
    <v-app-bar
      app
      color="primary"
      dark
    ><h2>Vue with Vuetify</h2>

      <v-spacer></v-spacer>

      <v-btn
        href="https://github.com/NickTicangenJr/temperature-converter"
        target="_blank"
        text
      >
        <span class="mr-2">Github Source</span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>
    </v-app-bar>

    <v-main>
      <TempConverter/>
    </v-main>
  </v-app>
</template>

<script>
import TempConverter from './components/TempConverter';

export default {
  name: 'App',

  components: {
    TempConverter,
  },

  data: () => ({
    //
  }),
};
</script>
