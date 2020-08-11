<template>
  <v-app>
    <v-app-bar app color="primary" dark>
      <v-container class="text-center">
        <v-btn text small>About</v-btn>
        <v-btn text small>Work</v-btn>
      </v-container>
    </v-app-bar>
      <section id="about-me">
        <div class="py-12"></div>

        <v-container class="text-center">
          <h2 class="display-2 font-weight-bold mb-3">JF Phaner</h2>
          <v-avatar
            class="elevation-12 mb-12"
            size="128"
          >
            <v-img src="https://cdn.vuetifyjs.com/images/john.png"></v-img>
          </v-avatar>
          <v-responsive
            class="mx-auto title font-weight-light mb-8"
            max-width="720"
          >
            Vuetify is the #1 component library for Vue.js and has been in active development since 2016. The goal of the project is to provide users with everything that is needed to build rich and engaging web applications using the Material Design specification. It accomplishes that with a consistent update cycle, Long-term Support (LTS) for previous versions, responsive community engagement, a vast ecosystem of resources and a dedication to quality components.
          </v-responsive>

          <v-btn
            color="grey"
            href="https://vuetifyjs.com"
            outlined
            large
          >
            <span class="grey--text text--darken-1 font-weight-bold">
              Resume
            </span>
          </v-btn>
          <v-btn
            color="grey"
            href="https://vuetifyjs.com"
            outlined
            large
          >
            <span class="grey--text text--darken-1 font-weight-bold">
              Linkedin
            </span>
          </v-btn>
        </v-container>

        <div class="py-12"></div>
      </section>
      <section>
        <v-row>

        </v-row>
      </section>
  </v-app>
</template>