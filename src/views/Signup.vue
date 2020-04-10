<template>
  <v-container>
    <v-row>
      <v-col>
        <v-form>
          <h1>Singup</h1>
          <v-text-field label="Email" type="email"></v-text-field>
          <v-autocomplete
            label="Which browser do you use?"
            :items="browsers"
          ></v-autocomplete>
          <v-file-input label="Attach profile picture"></v-file-input>
          <v-text-field
            label="Birthday"
            v-model="birthday"
            readonly
          ></v-text-field>
          <v-date-picker v-model="birthday"></v-date-picker>
          <v-checkbox label="Agree to Terms &amp; Conditions"></v-checkbox>
          <v-btn type="submit" color="primary">Submit</v-btn>
        </v-form>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      birthday: '',
      browsers: ['Chrome', 'Firefox', 'Safari', 'Edge', 'Brave']
    };
  }
};
</script>

<style lang="scss" scoped></style>
