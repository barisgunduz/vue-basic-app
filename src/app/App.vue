<template>
  <div>
    <Nav />
      <div class="container">
        <div class="row">
          <div class="col-sm-6 offset-sm-3">
            <div v-if="alert.message" :class="`alert ${alert.type}`">
              {{ alert.message }}
            </div>
            <router-view></router-view>
          </div>
        </div>
      </div>
  </div>
</template>

<script>
import { mapState, mapActions } from "vuex";
import Nav from './Nav'
export default {
  name: "app",
  components: {Nav},
  computed: {
    ...mapState({
      alert: (state) => state.alert,
      account: (state) => state.account,
    }),
  },
  methods: {
    ...mapActions({
      clearAlert: "alert/clear"
    }),
  },
  watch: {
    $route(to, from) {
      // clear alert on location change
      this.clearAlert();
    },
  },
};
</script>