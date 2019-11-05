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
          a(href="https://etherscan.io/address/0xB6422d505c27A0548ef9fD5F1Ee09195d0292e54") 0xB6422d505c27A0548ef9fD5F1Ee09195d0292e54
        p {{$t("scamBet", { amount: this.scamBalance })}}
        h2 {{$t("notScam")}}
        h3
          a(href="https://etherscan.io/address/0x1DB5bDE13E84Aa0f84282b73dBE92C5a4354fB29") 0x1DB5bDE13E84Aa0f84282b73dBE92C5a4354fB29
        p {{$t("notScamBet", { amount: this.notScamBalance })}}
        a.pt-4(href="https://github.com/backmeupplz/minterscam") {{$t("opensource")}}
</template>

<script lang="ts">
import Vue from "vue";
import * as store from "../plugins/store";
import Component from "vue-class-component";
import { i18n } from "../plugins/i18n";
import Web3 from "web3";
const web3 = new Web3(
  "https://mainnet.infura.io/v3/dd80994b42d540daa7c17d01bfbacd6d"
);

@Component
export default class Home extends Vue {
  scamBalance = "~";
  notScamBalance = "~";

  async mounted() {
    this.scamBalance = await web3.eth.getBalance(
      "0xB6422d505c27A0548ef9fD5F1Ee09195d0292e54"
    );
    this.notScamBalance = await web3.eth.getBalance(
      "0x1DB5bDE13E84Aa0f84282b73dBE92C5a4354fB29"
    );
  }
}
</script>
