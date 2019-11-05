<template lang="pug">
  v-app(:class='$store.state.dark ? "grey darken-4" : "grey lighten-4"')
    cookie-law(theme='blood-orange'
    :buttonText='$t("cookie.button")'
    :message='$t("cookie.message")')
    Navbar
    Snackbar
    v-content
      router-view
</template>

<script lang="ts">
import Navbar from "./components/Navbar.vue";
import Snackbar from "./components/Snackbar.vue";
import * as store from "./plugins/store";
const CookieLaw = require("vue-cookie-law");

export default {
  components: { Navbar, Snackbar, CookieLaw },
  beforeMount() {
    ((this as any).$vuetify.theme as any).dark = store.dark();
  }
};
</script>
