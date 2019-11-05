<template lang="pug">
  .v-container.pa-4
    // Main content
    v-layout(column
    justify-center
    align-center).text-center
      v-flex(xs12 md10)
        .headline.pb-4
          span(v-html='$t("home.info")')
        p {{$t('home.rules.register')}}
        p {{$t('home.rules.money')}}
        p {{$t('home.rules.success')}}
</template>

<script lang="ts">
import Vue from "vue";
import * as store from "../plugins/store";
import Component from "vue-class-component";
import { i18n } from "../plugins/i18n";

@Component
export default class Home extends Vue {}
</script>
