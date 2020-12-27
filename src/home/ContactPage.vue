<template>
  <div>
    <h4>
      {{ $t("body.homepage.hi") }} {{ account.user.firstName }}
      {{ account.user.lastName }}!
    </h4>
    <p>{{ $t("body.contactPage.header.formText") }}</p>
    <form @submit.prevent="handleSubmit">
      <div class="form-group">
        <label for="firstName">{{ $t("body.contactPage.form.name") }}</label>
        <input
          type="text"
          v-model="userForm.firstName"
          v-validate="'required'"
          name="firstName"
          class="form-control"
          :class="{ 'is-invalid': submitted && errors.has('firstName') }"
        />
        <div
          v-if="submitted && errors.has('firstName')"
          class="invalid-feedback"
        >
          {{ errors.first("firstName") }}
        </div>
      </div>
      <div class="form-group">
        <label for="email">{{ $t("body.contactPage.form.email") }}</label>
        <input
          type="email"
          v-model="userForm.email"
          v-validate="'required'"
          name="email"
          class="form-control"
          :class="{ 'is-invalid': submitted && errors.has('email') }"
        />
        <div v-if="submitted && errors.has('email')" class="invalid-feedback">
          {{ errors.first("email") }}
        </div>
      </div>
      <div class="form-group">
        <label for="phoneNumber">{{
          $t("body.contactPage.form.phoneNumber")
        }}</label>
        <input
          type="tel"
          v-model="userForm.phoneNumber"
          v-validate="'required'"
          name="phoneNumber"
          class="form-control"
          :class="{ 'is-invalid': submitted && errors.has('phoneNumber') }"
        />
        <div
          v-if="submitted && errors.has('phoneNumber')"
          class="invalid-feedback"
        >
          {{ errors.first("phoneNumber") }}
        </div>
      </div>
      <!-- <div class="form-group">
        <autocomplete
    :search="search"
    placeholder="Search for a country"
    aria-label="Search for a country"
    auto-select
  ></autocomplete>
      </div> -->
      <div class="form-group">
        <label for="searchCountry">{{
          $t("body.contactPage.form.searchForCountry")
        }}</label>
        <!-- <autocomplete :suggestions="countries" :selection.sync="value"></autocomplete> -->
        <autocomplete
          :search="search"
          auto-select
          name="searchCountry"
          :class="{ 'is-invalid': submitted && errors.has('searchCountry') }"
        ></autocomplete>
        <!-- <input
          :search="search"
          auto-select
          name="searchCountry"
          class="form-control"
          v-model="userForm.searchCountry"
          :class="{ 'is-invalid': submitted && errors.has('searchCountry') }"
        /> -->
      </div>
      <div class="form-group">
        <label for="comment">{{ $t("body.contactPage.form.comment") }}</label>
        <textarea
          name="comment"
          class="form-control"
          cols="30"
          rows="10"
          v-model="userForm.comment"
          :class="{ 'is-invalid': submitted && errors.has('comment') }"
        ></textarea>
      </div>
      <div class="form-group">
        <button class="btn btn-danger" :disabled="status.registering">
          {{ $t("body.contactPage.form.sendButton") }}
        </button>
        <img
          v-show="status.registering"
          src="data:image/gif;base64,R0lGODlhEAAQAPIAAP///wAAAMLCwkJCQgAAAGJiYoKCgpKSkiH/C05FVFNDQVBFMi4wAwEAAAAh/hpDcmVhdGVkIHdpdGggYWpheGxvYWQuaW5mbwAh+QQJCgAAACwAAAAAEAAQAAADMwi63P4wyklrE2MIOggZnAdOmGYJRbExwroUmcG2LmDEwnHQLVsYOd2mBzkYDAdKa+dIAAAh+QQJCgAAACwAAAAAEAAQAAADNAi63P5OjCEgG4QMu7DmikRxQlFUYDEZIGBMRVsaqHwctXXf7WEYB4Ag1xjihkMZsiUkKhIAIfkECQoAAAAsAAAAABAAEAAAAzYIujIjK8pByJDMlFYvBoVjHA70GU7xSUJhmKtwHPAKzLO9HMaoKwJZ7Rf8AYPDDzKpZBqfvwQAIfkECQoAAAAsAAAAABAAEAAAAzMIumIlK8oyhpHsnFZfhYumCYUhDAQxRIdhHBGqRoKw0R8DYlJd8z0fMDgsGo/IpHI5TAAAIfkECQoAAAAsAAAAABAAEAAAAzIIunInK0rnZBTwGPNMgQwmdsNgXGJUlIWEuR5oWUIpz8pAEAMe6TwfwyYsGo/IpFKSAAAh+QQJCgAAACwAAAAAEAAQAAADMwi6IMKQORfjdOe82p4wGccc4CEuQradylesojEMBgsUc2G7sDX3lQGBMLAJibufbSlKAAAh+QQJCgAAACwAAAAAEAAQAAADMgi63P7wCRHZnFVdmgHu2nFwlWCI3WGc3TSWhUFGxTAUkGCbtgENBMJAEJsxgMLWzpEAACH5BAkKAAAALAAAAAAQABAAAAMyCLrc/jDKSatlQtScKdceCAjDII7HcQ4EMTCpyrCuUBjCYRgHVtqlAiB1YhiCnlsRkAAAOwAAAAAAAAAAAA=="
        />
      </div>
    </form>
  </div>
</template>

<script>
import { mapState, mapActions } from "vuex";
import Autocomplete from "@trevoreyre/autocomplete-vue";
import LocaleSwitcher from "../components/LocaleSwitcher";

const countryList = [
  "Turkey",
  "United States of America",
  "United Kingdom",
  "Germany",
  "Sweden",
  "Kenya",
  "Brazil",
  "Zimbabwe",
  // { id: "TR", name: "Turkey" },
  // { id: "US", name: "United States of America" },
  // { id: "GB", name: "United Kingdom" },
  // { id: "DE", name: "Germany" },
  // { id: "SE", name: "Sweden" },
  // { id: "KE", name: "Kenya" },
  // { id: "BR", name: "Brazil" },
  // { id: "ZW", name: "Zimbabwe" },
];

export default {
  components: {
    Autocomplete,
  },
  data() {
    return {
      userForm: {
        firstName: "",
        email: "",
        phoneNumber: "",
        searchCountry: "",
        comment: "",
      },
      submitted: false,
    };
  },
  computed: {
    ...mapState("account", ["status"]),
    ...mapState({
      account: (state) => state.account,
    }),
  },
  methods: {
    ...mapActions("account", ["register"]),
    handleSubmit(e) {
      this.submitted = true;
      this.$validator.validate().then((valid) => {
        if (valid) {
          console.log(JSON.stringify(this.userForm));
        }
      });
    },
    search(input) {
      // const countryListUrl = `https://raw.githubusercontent.com/samayo/country-json/master/src/country-by-name.json`;
      // return new Promise((resolve) => {
      //   if (input.length < 2) {
      //     return resolve([]);
      //   }

      //   fetch(countryListUrl)
      //     .then((response) => response.json())
      //     .then((data) => {
      //       console.log(data)
      //       resolve(data);
      //     });
      // });
      if (input.length < 1) {
        return [];
      }
      return countryList.filter((country) => {
        return country.toLowerCase().startsWith(input.toLowerCase());
      });
    },
    setLocale(locale) {
      this.$LocaleSwitcher.locale = locale;
    },
  },
};
</script>

<style>
@import "../../node_modules/@trevoreyre/autocomplete-vue/dist/style.css";
</style>