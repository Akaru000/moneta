<template>
  <v-app>
    <v-app-bar app>
      <v-app-bar-nav-icon>
        <nuxt-link to="/" tag="div">
          <v-icon>mdi-bank</v-icon>
        </nuxt-link>
      </v-app-bar-nav-icon>
      <v-toolbar-title>
        <p class="body-1 my-0">{{ bank | name }}</p>
        <p class="body-1 my-0">{{ branch | name }}</p>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-toolbar-items>
        <h1>moneta</h1>
      </v-toolbar-items>
      <v-spacer></v-spacer>
      <v-toolbar-items>
        <center>
        <p class="title" text>{{ account | name }}様</p>
        </center>
      </v-toolbar-items>
    </v-app-bar>
    <v-content>
      <center class="title" text>{{ account | name }}様 ようこそ</center>
      <v-container fluid>
        <v-layout align-start justify-center>
          <v-flex xs12 sm12 md8 xl8>
            <nuxt />
          </v-flex>
        </v-layout>
      </v-container>
      <code v-if="debug">{{ $store.state }}</code>
    </v-content>
  </v-app>
 

</template>

<script>
import { mapGetters } from "vuex";

export default {
  data: () => ({
    debug: false,
  }),
  computed: {
    ...mapGetters("login", ["account", "branch", "bank"]),
  },
};
</script>
