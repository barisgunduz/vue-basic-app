<template>
  <div>
    <h4 v-if="account.user">{{ $t("body.homepage.hi") }} {{ account.user.firstName }}!</h4>
    <h4 v-if="!account.user">{{ $t("info.notLoggedIn") }}</h4>
    <div v-if="account.user">
      <p>
        {{ $t("body.homepage.dummyMessage") }}
      </p>
    </div>
  </div>
</template>

<script>
import { mapState, mapActions } from "vuex";
import LocaleSwitcher from "../components/LocaleSwitcher"

export default {
  methods: {
    setLocale(locale) {
      this.$LocaleSwitcher.locale = locale
    }
  },
  computed: {
    ...mapState({
      account: (state) => state.account
    }),
  },
};
</script>