<template lang="pug">
  .v-container.pa-4(style='maxWidth: 1000px; margin: auto')
    // Main content
    v-layout(column
    justify-center
    align-center).text-center
      v-flex(xs12 md10)
        .headline.pb-4
          span {{$t("home.info")}}
        p(v-for='premise in $t("home.premises")' v-html='premise')
        h2 {{$t("scam")}}
        h3
          a(href="https://etherscan.io/address/123") 123
        p {{$t("scamBet", { amount: 50 })}}
        h2 {{$t("notScam")}}
        h3
          a(href="https://etherscan.io/address/123") 123
        p {{$t("notScamBet", { amount: 10 })}}
        a.pt-4(href="https://github.com/backmeupplz/minterscam") {{$t("opensource")}}
</template>

<script lang="ts">
import Vue from "vue";
import * as store from "../plugins/store";
import Component from "vue-class-component";
import { i18n } from "../plugins/i18n";

@Component
export default class Home extends Vue {}
</script>
