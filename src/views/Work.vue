<template>
  <v-app>
        <v-container>
          <h1>My work</h1>
          <v-card>
          <h2>Pipou</h2>
            <v-row>
              <v-col cols="6">
                <v-responsive>
                  Vuetify is the #1 component library for Vue.js and has been in active development since 2016. The goal of the project is to provide users with everything that is needed to build rich and engaging web applications using the Material Design specification. It accomplishes that with a consistent update cycle, Long-term Support (LTS) for previous versions, responsive community engagement, a vast ecosystem of resources and a dedication to quality components.
                </v-responsive>
                <v-btn rounded>
                  <router-link to="/project1">See more</router-link>
                </v-btn>
              </v-col>
              <v-col cols="6">
                <v-img
                    src="https://images.unsplash.com/photo-1423784346385-c1d4dac9893a?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1950&q=80"
                    class="mb-4"
                    height="275"
                    max-width="100%">
                </v-img>
              </v-col>
            </v-row>
          <v-spacer></v-spacer>
          </v-card>
          <v-card>
          <h2>Pipou</h2>
            <v-row>
              <v-col cols="6">
                <v-responsive>
                  Vuetify is the #1 component library for Vue.js and has been in active development since 2016. The goal of the project is to provide users with everything that is needed to build rich and engaging web applications using the Material Design specification. It accomplishes that with a consistent update cycle, Long-term Support (LTS) for previous versions, responsive community engagement, a vast ecosystem of resources and a dedication to quality components.
                </v-responsive>
              </v-col>
              <v-col cols="6">
                <v-img
                    src="https://images.unsplash.com/photo-1423784346385-c1d4dac9893a?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1950&q=80"
                    class="mb-4"
                    height="275"
                    max-width="100%">
                </v-img>
              </v-col>
            </v-row>
          <v-spacer></v-spacer>
          </v-card>
          </v-container>
  </v-app>
</template>