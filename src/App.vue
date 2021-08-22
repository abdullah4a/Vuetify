<template>
  <v-app>
    <v-app-bar app color="success darken-2" light>
      <v-toolbar-title>Vuetify Login</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn
        v-for="link in links"
        :key="link"
        color="white"
        text
        rounded
        class="my-2"
      >
        {{ link }}
      </v-btn>
    </v-app-bar>
    <v-content>
      <!-- Login Section -->
      <v-card width="500px" class="mx-auto mt-9">
        <v-card-title>
          <h1 class="display-1" justify="center">Login</h1>
        </v-card-title>
        <v-card-text>
          <v-form>
            <!-- mdi-account-circle -->
            <v-text-field
              label="Username"
              prepend-icon="mdi-account"
            ></v-text-field>
            <v-text-field
              :type="showPassword ? 'text' : 'password'"
              label="Password"
              prepend-icon="mdi-lock"
              :append-icon="showPassword ? 'mdi-eye' : 'mdi-eye-off'"
              @click:append="showPassword = !showPassword"
            ></v-text-field>
          </v-form>
        </v-card-text>
        <v-divider></v-divider>
        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn color="success" text>Register</v-btn>
          <v-spacer></v-spacer>
          <v-btn color="info" text> Login</v-btn>
          <v-spacer></v-spacer>
        </v-card-actions>
      </v-card>
    </v-content>
    <v-footer color="primary lighten-1" padless>
      <v-col class="primary lighten-2 py-4 text-center white--text" cols="12">
        {{ new Date().getFullYear() }} — <strong>Vuetify</strong>
      </v-col>
    </v-footer>
  </v-app>
</template>

<script lang="ts">
import Vue from "vue";
// import HelloWorld from "./components/HelloWorld.vue";
import Component from "vue-class-component";

// Define the component in class-style
@Component
export default class Counter extends Vue {
  private showPassword = false;
  private links = ["Home", "About Us", "Login"];
}
</script>
