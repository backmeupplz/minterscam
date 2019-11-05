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
import { i18n } from "./plugins/i18n";
const CookieLaw = require("vue-cookie-law");

export default {
  components: { Navbar, Snackbar, CookieLaw },
  beforeMount() {
    ((this as any).$vuetify.theme as any).dark = store.dark();
    document.title = i18n.t("title") as string;
  }
};
</script>
