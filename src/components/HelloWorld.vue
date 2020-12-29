<template>
  <v-container>
    <v-row>
      <v-col>
        <v-img
          :src="require('../assets/logo.svg')"
          class="my-3"
          contain
          height="200"
        ></v-img>
      </v-col>
    </v-row>
    <v-row>
      <v-col class="d-inline-flex justify-center">
        <h1 class="display-2">
          Welcome
        </h1>
      </v-col>
    </v-row>
    <v-row>
      <v-col class="d-inline-flex justify-center">
        <p class="subheading font-weight-regular">
          For more information about this application please see this
          <a href="https://github.com/p2well/vuetify-dashboard" target="_blank"
            >GitHub repository</a
          >
        </p>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped></style>
