<template>
  <v-app>
    <v-app-bar
      app
      color="primary"
      dark
    >
      <div class="d-flex align-center" @click="$router.push({ name: 'Home' })">
        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
          transition="scale-transition"
          width="40"
        />

        <v-img
          alt="Vuetify Name"
          class="shrink mt-1 hidden-sm-and-down"
          contain
          min-width="100"
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-name-dark.png"
          width="100"
        />
      </div>

      <v-spacer></v-spacer>

      <v-btn text @click="changeLocale">
        {{ $i18n.locale }}
      </v-btn>

      <v-btn
        :to="{ name: 'About' }"
        text
      >
        <span class="mr-2">من نحن</span>
        <v-icon>mdi-account-check</v-icon>
      </v-btn>

      <v-btn
        href="https://github.com/vuetifyjs/vuetify/releases/latest"
        target="_blank"
        text
      >
        <span class="mr-2">آخر الإصدارات</span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>
    </v-app-bar>

    <v-main>
      <router-view/>
    </v-main>
  </v-app>
</template>

<script>

export default {
  name: 'App',

  data: () => ({
    //
  }),

  methods: {
    changeLocale () {
      this.$i18n.locale = this.$i18n.locale === 'ar' ? 'en' : 'ar'
      this.$vuetify.rtl = this.$i18n.locale === 'ar'
    }
  },

  mounted () {
    this.$vuetify.rtl = true
  }
}
</script>
