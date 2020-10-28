<template>
  <v-app id="top">
    <div class="menu mobile_menu d-flex d-sm-none">
      <v-btn @click="$vuetify.goTo('#work', options)">
        <span>
          Work
        </span>
      </v-btn>
      <v-btn @click="$vuetify.goTo('#experience', options)">
        <span>
          Experience
        </span>
      </v-btn>
      <v-btn @click="$vuetify.goTo('#about', options)">
        <span>
          About
        </span>
      </v-btn>
    </div>
    <div class="scroll-to-top hide" id="scrollToTop">
      <v-btn ref="button" @click="$vuetify.goTo('#top', options)">
        Back to top
      </v-btn>
    </div>
      <section>
        <div class="py-12" id="top"></div>
        <v-container class="text-center">
          <h1>Hi ! I'm JF</h1>
          <h4 class="mb-6">Product designer, UX teacher and project manager</h4>
          <v-responsive class="mx-auto mb-8">
            <p>I am an accomplished product designer with more than 10 years of experience and 6 years as a UX designer. I love building business applications for Airports, Hospitals, Smart buildings, Retail Stores and the Supply chain.</p>
          </v-responsive>
        </v-container>
        <div class="header container text-center d-none d-sm-block sticky" id="myHeader">
          <v-btn @click="$vuetify.goTo('#work', options)">
            <span>
              Work
            </span>
          </v-btn>
          <v-btn @click="$vuetify.goTo('#experience', options)">
            <span>
              Experience
            </span>
          </v-btn>
          <v-btn @click="$vuetify.goTo('#about', options)">
            <span>
              About
            </span>
          </v-btn>
        </div>
        <div class="content"></div>
        <v-container>
          <div class="py-12"></div>
          <h2 id="work" class="text-center">Work</h2>
          <p class="text-center">Selected works from 2013-2020</p>
          <v-carousel>
              <v-carousel-item :key="i" v-for="(project, i) in projects">
                  <v-dialog v-model="dialog">                
                      <template v-slot:activator="{ on, attrs }">
                          <v-card v-bind="attrs" v-on="on" class="mx-auto my-12" max-width="550">
                              <v-img class="card_content" height="600" :src="project.src1">
                              </v-img>
                              <div class="tip">
                                <v-card-text>
                                  <v-chip class="card_subtitle" v-text="project.title"></v-chip>
                                  <p v-text="project.subtitle"></p>
                                  <v-chip-group v-model="selection" active-class="deep-purple accent-4 white--text" column>
                                    <v-chip v-text="project.chip1"></v-chip>
                                    <v-chip v-text="project.chip2"></v-chip>
                                    <v-chip v-text="project.chip3"></v-chip>
                                    <v-chip v-text="project.chip4"></v-chip>
                                  </v-chip-group>
                                </v-card-text>
                              </div>
                          </v-card>
                      </template>
                      <v-card v-bind="attrs" v-on="on" max-width="900" class="project_card" @click="dialog = false">
                          <v-container>
                              <div class="py-4"></div>
                              <h2 v-text="project.title"></h2>
                              <p v-text="project.subtitle"></p>
                              <div class="py-4"></div>
                              <p v-text="project.context1"></p>
                              <p v-text="project.context2"></p>
                              <p v-text="project.context3"></p>
                              <div class="py-4"></div>
                              <p v-text="project.text1"></p>
                              <v-img class="card_content" height="300" :src="project.src2"></v-img>
                              <h3 v-text="project.title2"></h3>
                              <p v-text="project.text2"></p>
                              <v-img class="card_content" height="300" :src="project.src3"></v-img>
                              <h3 v-text="project.title3"></h3>
                              <p v-text="project.text3"></p>
                              <v-img class="card_content" height="300" :src="project.src4"></v-img>
                              <h3 v-text="project.title4"></h3>
                              <p v-text="project.text4"></p>
                              <v-card-actions>
                              <v-spacer></v-spacer>
                              </v-card-actions>
                          </v-container>
                      </v-card>
                  </v-dialog>
              </v-carousel-item>
          </v-carousel>
        </v-container>
        <v-container class="experience_container">
          <div class="py-12"></div>
          <h2 id="experience" class="my-3 text-center">Experience</h2>
          <v-stepper dark v-model="e1" non-linear alt-labels vertical>
            <div class="py-4" id="top"></div>
            <v-stepper-items :key="e" v-for="(experience, e) in experiences">
              <v-stepper-step editable :step="experience.step" v-text="experience.title"></v-stepper-step>
              <v-stepper-content :step="experience.step">
                <v-row class="mx-auto mb-8">
                  <v-col cols="12" md="4">
                    <v-img class="card_content" height="300" :src="experience.src"></v-img>
                  </v-col>
                  <v-col cols="12" md="8">
                    <h3 v-text="experience.date"></h3>
                    <p v-text="experience.text"></p>
                    <p v-text="experience.companies"></p>
                  </v-col>
                </v-row>
              </v-stepper-content>
            </v-stepper-items>
          </v-stepper>
        </v-container>
        <v-container>
          <div class="py-12"></div>
          <h2 id="about" class="my-3 text-center">About me</h2>
          <v-row class="mx-auto mb-8">
            <v-col cols="12" lg="6">
                <v-img style="min-height: 50%; max-height: 80%;" src="https://cdn.dribbble.com/users/2742725/screenshots/11545309/media/b5d5be42fb7f1e95667efce885a8f585.png"></v-img>
            </v-col>
            <v-col cols="12" lg="6">
              <h4 class="mb-6">Senior UX designer and teacher</h4>
              <ul class="mb-6">
                <li>Lean UX design methods</li>
                <li>SAAS Product & service oriented</li>
                <li>I started teaching UX this year</li>
              </ul>
              <h4 class="mb-6">Project manager</h4>
              <ul class="mb-6">
                <li>Strong experience in Agile projects</li>
                <li>I manage teams and I can help them achieve</li>
                <li>Trued communication skills</li>
              </ul>
              <h4 class="mb-6">Front-end developer</h4>
              <ul class="mb-6">
                <li>I can integrate Front-end web technologies</li>
                <li>I'm familiar with VueJs, Github and Netlify</li>
                <li>Like this website</li>
              </ul>
            </v-col>
          </v-row>
        </v-container>

        <v-container>
            <h3 class="my-3">Principles from experience</h3>
            <ul>
              <li><strong>Know your users</strong> : <span> treat indirect information cautiously.</span></li>
              <li>Focus on user goals before business needs: Business will bloom if users are happy</li>
              <li>Keep it ligt : Doesn't mean faster</li>
              <li>collaborative process</li>
            </ul>
        </v-container>
        <v-container>
          <div class="py-12" id="contact"></div>
          <h2 class="my-3">Contact</h2>
          <v-btn href="https://vuetifyjs.com">
            <span>
              jfphaner@gmail.com
            </span>
          </v-btn>
          <v-btn href="https://vuetifyjs.com">
            <span>
              +33 06 98 63 39
            </span>
          </v-btn>
          <v-btn href="https://vuetifyjs.com">
            <span>
              Resume
            </span>
          </v-btn>
        </v-container>
      </section>
  </v-app>
</template>

<script>

document.addEventListener('DOMContentLoaded', function() {
  // When the event DOMContentLoaded occurs, it is safe to access the DOM

  // When the user scrolls the page, execute myFunction 
  window.addEventListener('scroll', myFunction);

  // Get the navbar
  var header = document.getElementById("myHeader");
  var scrollToTop = document.getElementById("scrollToTop");

  // Get the offset position of the navbar
  var sticky = header.offsetTop;

  // Add the sticky class to the navbar when you reach its scroll position. 
  // Remove "sticky" when you leave the scroll position

  function myFunction() {
    if (window.pageYOffset > sticky) {
      header.classList.add("sticky");
      scrollToTop.classList.remove("hide");
    } else {
      header.classList.remove("sticky");
      scrollToTop.classList.add("hide");
    }
  }
})

  export default {
    data () {
      return {
        dialog: false,
        showBackToTop: false,
        e1: 1,
        projects: [
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
          }
        ],
        experiences: [
          {
              step: '1',
              src: 'https://cdn.vuetifyjs.com/images/cards/halcyon.png',
              date: '',
              title: 'Webdesigner - 2007',
              text: 'After completing my Scientific Baccalaureate, i studied Webdesign at Supcrea Grenoble in 2004-2007. I then worked for 5 years as a web and graphic designer, mostly for E-commerce and a couple of years in an agency in Montreal.',
              companies: 'Companies : Fitness boutique, Sport Aix Trem and Zip communication.',
          },
          {
              step: '2',
              src: 'https://cdn.vuetifyjs.com/images/cards/halcyon.png',
              date: '',
              title: 'Lead designer - 2012',
              text: 'When i came back to France and i was offered a job as a Lead designer for Visioglobe in Grenoble. Because it was mostly a pure tech company, my responsibilities where to lead design on all the products of the company.',
              companies: 'Companies : Visioglobe',
          },
          {
              step: '3',
              src: 'https://cdn.vuetifyjs.com/images/cards/halcyon.png',
              date: '',
              title: 'Ux Designer - 2014',
              text: 'I started to get interested about UX when in 2013 i worked on a project with an experienced computer ergonomics engineer who mentored me, i then followed courses online on how to implement user centered design in Visioglobe many products. After a couple of years i then went back to school in 2017-2018 in order to obtain the Digital Project Director diploma at the Gobelins school in Paris.',
              companies: 'Companies : Visioglobe, Wynd, Accenture.',
          },
          {
              step: '4',
              src: 'https://cdn.vuetifyjs.com/images/cards/halcyon.png',
              date: '',
              title: 'Freelance - 2020',
              text: 'After getting a lot of experiences in startups and agencies, i started my own company with many services such as UX product design, Product management and UX mentoring and teaching.',
              companies: 'Clients : Gatoreviews, Rossignol, Botanic, Peexeo, Molitor Paris.',
          }
        ],
      }
    }
  }
  
</script>
