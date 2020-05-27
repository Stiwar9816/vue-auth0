<template>
  <v-app>
    <v-app-bar app color="primary" dark>
      <v-toolbar-title>
        <span>Auth0 With Vue/Vuefity</span>
      </v-toolbar-title>

      <v-spacer></v-spacer>
      <v-btn class="mr-2" to="/" text>Home</v-btn>
      <v-btn class="mr-2" to="/about" text>About</v-btn>
      <v-btn class="mr-2" to="/contact" text>Contact</v-btn>
      <v-btn class="mr-2" to="/members" text>Members</v-btn>
      <v-btn @click="logout" v-if="this.$store.state.userIsAuthorized" text
        >Logout</v-btn
      >
    </v-app-bar>

    <v-content>
      <router-view></router-view>
    </v-content>
  </v-app>
</template>

<script>
export default {
  name: "App",
  data() {
    return {};
  },
  methods: {
    logout() {
      this.$store.dispatch("auth0Logout");
      console.log("Logging out");
    },
  },
};
</script>
