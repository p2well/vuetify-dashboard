<template>
  <v-app>
    <v-app-bar app color="primary" dark>
      <v-toolbar-title>{{ appName }}</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn
        v-for="link in links"
        :key="`${link.label}-footer-link`"
        text
        rounded
        :to="link.url"
      >
        {{ link.label }}
      </v-btn>
      <v-switch
        v-model="darkThemeSwitch"
        @change="toggleToDarkTheme"
        label="Dark Theme"
        color="white"
        class="ml-8"
      ></v-switch>
    </v-app-bar>
    <v-content>
      <router-view></router-view>
    </v-content>
    <v-footer color="primary lighten-1" padless>
      <v-row justify="center" no-gutters>
        <v-btn
          v-for="link in links"
          :key="`${link.label}-footer-link`"
          color="white"
          text
          rounded
          class="my-2"
          :to="link.url"
        >
          {{ link.label }}
        </v-btn>
        <v-col class="primary lighten-2 py-4 text-center white--text" cols="12">
          {{ new Date().getFullYear() }} — <strong>{{ appName }}</strong>
        </v-col>
      </v-row>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: 'App',
  components: {},
  data() {
    return {
      appName: 'Vuetify Dashboard',
      darkThemeSwitch: false,
      links: [
        {
          label: 'Home',
          url: '/'
        },
        {
          label: 'Login',
          url: '/login'
        },
        {
          label: 'Singup',
          url: '/signup'
        },
        {
          label: 'Dashboard',
          url: '/dashboard'
        }
      ]
    }
  },
  methods: {
    toggleToDarkTheme() {
      this.$vuetify.theme.themes.dark.anchor = '#82B1FF'
      this.$vuetify.theme.dark = !this.$vuetify.theme.dark
    }
  }
}
</script>
