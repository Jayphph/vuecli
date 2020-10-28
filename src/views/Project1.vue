<template>
  <v-app>
    <v-container>
        <v-dialog :key="i" v-for="(item, i) in items" v-model="dialog">                
            <template v-slot:activator="{ on, attrs }">
                <v-card v-bind="attrs" v-on="on" class="mx-auto my-12" max-width="550">
                    <v-img class="card_content" height="600" :src="item.src1">
                    </v-img>
                    <div class="tip">
                        <v-card-text>
                        <v-chip class="card_subtitle" v-text="item.title"></v-chip>
                        <p v-text="item.subtitle"></p>
                        <v-chip-group v-model="selection" active-class="deep-purple accent-4 white--text" column>
                            <v-chip v-text="item.chip1"></v-chip>
                            <v-chip v-text="item.chip2"></v-chip>
                            <v-chip v-text="item.chip3"></v-chip>
                            <v-chip v-text="item.chip4"></v-chip>
                        </v-chip-group>
                        </v-card-text>
                    </div>
                </v-card>
            </template>
            <v-card v-bind="attrs" v-on="on" max-width="900" class="project_card" @click="dialog = false">
                <v-container>
                    <div class="py-4"></div>
                    <h1 v-text="item.title" class="text-center"></h1>
                    <p v-text="item.subtitle"></p>
                    <div class="py-4"></div>
                    <h4 class="text-center">Context</h4>
                    <p v-text="item.context1"></p>
                    <p v-text="item.context2"></p>
                    <p v-text="item.context3"></p>
                    <p v-text="item.text1"></p>
                    <v-img class="card_content" height="300" :src="item.src2"></v-img>
                    <h2 v-text="item.title2" class="text-center"></h2>
                    <p v-text="item.text2"></p>
                    <v-img class="card_content" height="300" :src="item.src3"></v-img>
                    <h2 v-text="item.title3" class="text-center"></h2>
                    <p v-text="item.text3"></p>
                    <v-img class="card_content" height="300" :src="item.src4"></v-img>
                    <h2 v-text="item.title4" class="text-center"></h2>
                    <p v-text="item.text4"></p>
                    <v-card-actions>
                    <v-spacer></v-spacer>
                    </v-card-actions>
                </v-container>
            </v-card>
        </v-dialog>
    </v-container>


    <!--<section id="about-me">

                    <h4>“As simple as legos”</h4>
                    <p>
                    Originally, their was a first functional version of the application but without a UX / UI approach, so we were asked, the lead dev at the source of the project and me, to develop a new version “as simple as legos”. My work began at the software design stage with a user-centered approach, by investigating user needs with the sales and project teams. A first round of sketching and prioritization of information, define a sustainable evolutionary strategy and take into account all types of uses and goals.
                    </p>
                    <v-img src="https://images.unsplash.com/photo-1423784346385-c1d4dac9893a?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1950&q=80"></v-img>
                    <div class="py-8"></div>
                    <h4>A specialized business process</h4>
                    <p>
                    Before the advent of VisioMapeditor, 2D vector plans were drawn with Adobe Illustrator and Autocad by specialists. Our drawing process used strong technical constraints and the use of Illustrator is reserved for experts. One of our first problem was to collect the key features of Illustrator and Autocad in order to list the mandatory features to create an MVP and to re-imagine them simpler for our less experienced users.
                    </p>
                    <div class="py-8"></div>
                    <h4>The user-centered design begins</h4>
                    <p>
                    The second step was to define our users in a precise way and to list their goals, their objectives, always with the theme: create a box of Lego. Different users were identified. An important criterion was put forward and this revealed very contrasted among these people: the “power user” aspect, in other words the ease of the user to learn new software, to appropriate it as well as the level of IT culture of the user. 'user. 
                    </p>
                    <v-img src="https://images.unsplash.com/photo-1423784346385-c1d4dac9893a?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1950&q=80"></v-img>
                    <div class="py-8"></div>
                    <p>
                    After having defined these 2 issues, a classic period of UX project with a Lean UX approach starts: Specifying personas, story writing and ideation, storyboard tests and iterations, the development of the interface could begin.
                    </p>
                    <p>
                    From these studies were produced workflows to offer a compartmentalized and contextualized interface, adapted to different levels of learning. Following the first delivery 4 years ago, the product has evolved a lot and I actively participated in its development by integrating user feedback.
                    </p>
                    <div class="py-4"></div>
                    <h4>Constantly evolving</h4>
                    <p>
                    Today the graphic designers team all only use VisioMapeditor and do without illustrator, so we have achieved our initial objective. But a real goal in the long term and to create a product full of features such as collaborative editing and permanent backup. A next version even closer to the user will see the light of day in the medium term, following the evolution of our offer and the improvement of our work processes.
                    </p>
                </v-col>
            </v-row>
        </v-container>
    </section>-->
  </v-app>
</template>

<script>
  export default {
    data () {
      return {
      dialog: false,
      items: [
        {
          title: 'VisioMapEditor',
          chip1: 'UX design',
          chip2: 'UI design',
          chip3: 'User Research',
          chip4: 'User testing',
          src1: 'https://cdn.dribbble.com/users/2742725/screenshots/11545309/media/b5d5be42fb7f1e95667efce885a8f585.png',
          src2: 'https://cdn.dribbble.com/users/1494589/screenshots/14452688/media/87545cf803d96929e2614cc008616400.png',
          src3: 'https://cdn.dribbble.com/users/1494589/screenshots/14452688/media/87545cf803d96929e2614cc008616400.png',
          subtitle: 'A total reconvertion of a complex business application for a wider audience.,',
          context1: 'My role: Lead designer (Ux & Front dev)',
          context2: 'Date: 2013-2015',
          context3: '',
          context4: '',
          title1: 'As simple as legos',
          text1: 'Visioglobe offers its customers a 3D visualization solution of architectural plans on mobiles and Web, intended for large public in the form of an SDK. In order to let the customers edit and modify the plans after delivery, the VisioMapEditor software was created, for reasons of scalability and differentiation from the competition.',
          title2: 'Title 2',
          text2: 'Originally, their was a first functional version of the application but without a UX / UI approach, so we were asked, the lead dev at the source of the project and me, to develop a new version “as simple as legos”. My work began at the software design stage with a user-centered approach, by investigating user needs with the sales and project teams. A first round of sketching and prioritization of information, define a sustainable evolutionary strategy and take into account all types of uses and goals.',
          title3: 'Title 2',
          text3: 'Before the advent of VisioMapeditor, 2D vector plans were drawn with Adobe Illustrator and Autocad by specialists. Our drawing process used strong technical constraints and the use of Illustrator is reserved for experts. One of our first problem was to collect the key features of Illustrator and Autocad in order to list the mandatory features to create an MVP and to re-imagine them simpler for our less experienced userse',
          title4: 'Title 2',
          text4: 'The second step was to define our users in a precise way and to list their goals, their objectives, always with the theme: create a box of Lego. Different users were identified. An important criterion was put forward and this revealed very contrasted among these people: the “power user” aspect, in other words the ease of the user to learn new software, to appropriate it as well as the level of IT culture of the user.',
        },
        {
          src1: 'https://cdn.vuetifyjs.com/images/cards/halcyon.png',
          title: 'Halcyon Days',
          artist: 'Ellie Goulding',
        },
        {
          src1: 'https://cdn.vuetifyjs.com/images/cards/halcyon.png',
          title: 'Halcyon Days',
          artist: 'Poupie Golwing',
        },
      ],
    }
    }
  }
</script>

<style>

</style>