<template>
  <div>
    <h4 v-if="account.user">{{ $t("body.homepage.hi") }} {{ account.user.firstName }}!</h4>
    <h4 v-if="!account.user">{{ $t("info.notLoggedIn") }}</h4>
    <div v-if="account.user">
      <p>
        {{ $t("body.homepage.dummyMessage") }}
      </p>
      <!-- <em v-if="users.loading">{{ $t("info.loading") }}</em>
      <span v-if="users.error" class="text-danger"
        >{{ $t("info.error") }}: {{ users.error }}</span
      >
      <ul v-if="users.items">
        <li v-for="user in users.items" :key="user.id">
          {{ user.firstName + " " + user.lastName }}
          <span v-if="user.deleting"><em> - {{ $t("info.deleting") }}</em></span>
          <span v-else-if="user.deleteError" class="text-danger">
            - {{ $t("info.error") }}: {{ user.deleteError }}</span
          >
          <span v-else>
            -
            <a @click="deleteUser(user.id)" class="text-danger">{{ $t("info.delete") }}</a></span
          >
        </li>
      </ul> -->
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
      account: (state) => state.account,
      users: (state) => state.users.all,
    }),
  },
  created() {
    this.getAllUsers();
  },
  methods: {
    ...mapActions("users", {
      getAllUsers: "getAll",
      deleteUser: "delete",
    }),
  },
};
</script>