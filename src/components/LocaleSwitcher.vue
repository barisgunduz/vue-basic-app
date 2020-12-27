<template>
  <div class="locale-switcher nav-link">
    <select v-model="$i18n.locale">
      <option value="en">{{ $t("nav.localeSwitcher.en") }}</option>
      <option value="tr">{{ $t("nav.localeSwitcher.tr") }}</option>
    </select>
  </div>
</template>

<script>
import LocaleSwitcher from "../components/LocaleSwitcher";
export default {
  methods: {
    setLocale(locale) {
      this.$LocaleSwitcher.locale = locale;
    },
  },
};
</script>