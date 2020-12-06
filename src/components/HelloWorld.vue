<template>
  <v-app id="top">
    <div class="menu mobile_menu d-flex d-sm-none">
      <v-btn class="nav_button" @click="$vuetify.goTo('#work', options)">
        <span>
          Work
        </span>
      </v-btn>
      <v-btn class="nav_button" @click="$vuetify.goTo('#experience', options)">
        <span>
          Experience
        </span>
      </v-btn>
      <v-btn class="nav_button" @click="$vuetify.goTo('#about', options)">
        <span>
          About
        </span>
      </v-btn>
    </div>
      <section id="top">
        <div class="py-12"></div>
        <v-container class="text-center">
          <h1>Hi ! I'm JF</h1>
          <h4 class="mb-6">Product designer, UX teacher and project manager</h4>
          <v-responsive class="mx-auto mb-8">
            <p>I am an accomplished product designer with more than 10 years of experience and 6 years as a UX designer. I love building business applications for Airports, Hospitals, Smart buildings, Retail Stores and the Supply chain.</p>
          </v-responsive>
        </v-container>
        <div class="header-container d-none d-sm-block">
          <div id="myHeader" class="header container text-center d-none d-sm-block">
            <div class="hidden-nav-button">
            </div>
            <v-btn class="nav_button" @click="$vuetify.goTo('#work', options)">
              <span>
                Work
              </span>
            </v-btn>
            <v-btn class="nav_button" @click="$vuetify.goTo('#experience', options)">
              <span>
                Experience
              </span>
            </v-btn>
            <v-btn class="nav_button" @click="$vuetify.goTo('#about', options)">
              <span>
                About
              </span>
            </v-btn>
            <div class="hidden-nav-button">
              <div id="scrollToTop" class="hide">
                <v-btn class="nav_button" ref="button" @click="$vuetify.goTo('#top', options)">
                    <v-icon>mdi-arrow-up</v-icon>
                </v-btn>
              </div>
            </div>
          </div>
        </div>
        <v-container class="work">
  
          <h2 id="work" class="text-center">Work</h2>
          <p class="text-center">Selected works from 2013-2020</p>
          <v-carousel 
            :cycle="cycle"
            :show-arrows="false"
            hide-delimiter-background
            delimiter-icon="mdi-circle-medium"
          >
              <v-carousel-item :key="i" v-for="(project, i) in projects">
                  <v-dialog v-model="dialog[`project${i}`]" max-width="880" scrollable :key="`dialog-${i}`">                
                      <template v-slot:activator="{ on, attrs }">
                          <v-card v-bind="attrs" v-on="on" class="mx-auto my-8" max-width="550">
                              <v-img class="card_content" height="500" :src="project.coverimg1">
                              </v-img>
                              <div class="tip">
                                <v-card-text>
                                  <h5 v-text="project.title"></h5>
                                  <p v-text="project.subtitle"></p>
                                </v-card-text>
                              </div>
                          </v-card>
                      </template>
                      <v-card class="project_card" @click="dialog[`project${i}`] = false" :key="`card-${i}`">
                        <v-card-title>
                          <h5 v-text="project.title"></h5>
                          <v-spacer></v-spacer>
                          <span class="close_card">Click anywhere to close</span>
                        </v-card-title>
                        <v-divider></v-divider>
                        <v-card-text>
                          <v-container class="card_container">

                            <h5 v-text="project.subtitle"></h5>
                            <div class="py-4"></div>
                            <p class="dimmed context"><span class="context_type">Role</span><span v-text="project.context1"></span></p>
                            <p class="dimmed context"><span class="context_type">Date</span><span v-text="project.context2"></span></p>
                            <p class="dimmed context"><span class="context_type">Company</span><span v-text="project.context3"></span></p>
                            <p class="dimmed context"><span class="context_type">Goal</span><span v-text="project.context4"></span></p>
                            <p class="dimmed context"><span class="context_type">Gains</span><span v-text="project.context5"></span></p>
                            <div class="py-4"></div>
                            <p v-text="project.text1"></p>
                          </v-container>
                          <v-img class="card_content" height="300" :src="project.img1"></v-img>
                          <p class="dimmed imgcaption"><span v-text="project.captionimg1"></span></p>
                          <v-container class="card_container">
                            <h5 v-text="project.title2"></h5>
                            <p v-text="project.text2"></p>
                          </v-container>
                          <v-img class="card_content" height="300" :src="project.img2"></v-img>
                          <p class="dimmed imgcaption"><span v-text="project.captionimg2"></span></p>
                          <v-container class="card_container">
                            <h5 v-text="project.title3"></h5>
                            <p v-text="project.text3"></p>
                          </v-container>
                          <v-img class="card_content" height="300" :src="project.img3"></v-img>
                          <p class="dimmed imgcaption"><span v-text="project.captionimg3"></span></p>
                          <v-container class="card_container">
                            <h5 v-text="project.title4"></h5>
                            <p v-text="project.text4"></p>
                          </v-container>
                        </v-card-text>
                      </v-card>
                  </v-dialog>
              </v-carousel-item>
          </v-carousel>
        </v-container>
        <v-container class="experience_container">
          <h2 id="experience" class="py-6 mb-6 text-center">Experience</h2>
          <v-expansion-panels accordion>
            <v-expansion-panel
               :key="e" v-for="(experience, e) in experiences"
            >
              <v-expansion-panel-header>
                 <span v-text="experience.title"></span> 
              </v-expansion-panel-header>
              <v-expansion-panel-content>
                <v-row class="mb-6">
                  <v-col cols="12" sm="5">
                    <v-img class="card_content" height="250" :src="experience.src"></v-img>
                  </v-col>
                  <v-col cols="12" sm="7">
                    <h3 v-text="experience.date"></h3>
                    <p v-text="experience.text"></p>
                    <p v-text="experience.companies"></p>
                  </v-col>
                </v-row>
              </v-expansion-panel-content>
            </v-expansion-panel>
          </v-expansion-panels>

          <!--
          <v-stepper dark v-model="e1" non-linear alt-labels vertical>
            <div class="py-4" id="top"></div>
            <v-stepper-items :key="e" v-for="(experience, e) in experiences">
              <v-stepper-step editable :step="experience.step" v-text="experience.title"></v-stepper-step>
              <v-stepper-content :step="experience.step">
                <v-row class="mb-6">
                  <v-col cols="12" sm="5">
                    <v-img class="card_content" height="250" :src="experience.src"></v-img>
                  </v-col>
                  <v-col cols="12" sm="7">
                    <h3 v-text="experience.date"></h3>
                    <p v-text="experience.text"></p>
                    <p v-text="experience.companies"></p>
                  </v-col>
                </v-row>
              </v-stepper-content>
            </v-stepper-items>
          </v-stepper>
          -->

        </v-container>
        <v-container>
            <div class="py-16" id="top"></div>
          <h2 id="about" class="my-3 text-center">About me</h2>
          <v-row class="mx-auto mb-8">
            <v-col cols="12" sm="7">
              <h5>Senior UX designer and teacher</h5>
              <ul class="mb-6">
                <li>Lean UX design methods</li>
                <li>SAAS Product & service oriented</li>
                <li>I started teaching UX this year</li>
              </ul>
              <h5>Project manager</h5>
              <ul class="mb-6">
                <li>Strong experience in Agile projects</li>
                <li>I manage teams and I can help them achieve</li>
                <li>Trued communication skills</li>
              </ul>
              <h5>Front-end developer</h5>
              <ul class="mb-6">
                <li>I can integrate Front-end web technologies</li>
                <li>I'm familiar with VueJs, Github and Netlify</li>
                <li>Like this website</li>
              </ul>
              <strong class="my-3 d-none d-sm-block">Principles from experience</Strong>
              <ul class="d-none d-sm-block">
                <li>Know your users: treat indirect information cautiously</li>
                <li>Focus on user goals before business needs: Business will bloom if users are happy</li>
                <li>Keep it ligt: Less deliverables and more key elements</li>
                <li>All projects are a collaborative process</li>
              </ul>
            </v-col>
            <v-col cols="12" sm="5">
              <v-img height="250" src="https://cdn.dribbble.com/users/2742725/screenshots/11545309/media/b5d5be42fb7f1e95667efce885a8f585.png"></v-img>
              <div class="py-6"></div>
              <div class="contact">
                <v-btn class="link_button" href="https://vuetifyjs.com">
                  <span>
                    Call me: +33 06 98 63 39
                  </span>
                </v-btn>
                <v-btn class="link_button" href="mailto:jfphaner@gmail.com">
                  <span>
                    Send me an email 
                  </span>
                </v-btn>
                <v-btn class="link_button" href="https://vuetifyjs.com">
                  <span>
                    Download my resume
                  </span>
                </v-btn>
                <v-btn class="link_button" href="https://vuetifyjs.com">
                  <span>
                    Connect on LinkedIn
                  </span>
                </v-btn>
              </div>
            </v-col>
          </v-row>
        </v-container>
      </section>
      <section id="footer">
        <v-container class="text-center">
          <p>
            2020 JF Phaner, all rights reserved
          </p>
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
  console.log("🚀 ~ file: HelloWorld.vue ~ line 268 ~ document.addEventListener ~ sticky", sticky)

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
        dialog: {},
        cycle: false,
        showBackToTop: false,
        e1: 1,
        projects: [
          {
            title: 'VisioMapEditor',
            chip1: 'UX design',
            chip2: 'UI design',
            chip3: 'User Research',
            chip4: 'User testing',
            coverimg1: '../Img/mapeditor2.png',
            img1: '../Img/mapeditor1.7.png',
            captionimg1: 'VisioMapEditor first version',
            img2: '../Img/vme03.jpg',
            captionimg2: 'Sketches with the dev team',
            img3: '../Img/mapeditor2.png',
            captionimg3: 'VisioMapEditor 2',
            subtitle: 'From a specialist tool to a box of Legos',
            context1: 'Lead designer (Ux & Front dev)',
            context2: '2013-2015',
            context3: 'www.visioglobe.com',
            context4: 'Reduce training time',
            context5: 'From weeks to days',
            title1: 'A total reconvertion of a complex Web App.',
            text1: 'Visioglobe offers an indoor guiding SAAS solution for Airports, Malls, Smart cities, etc ... and their customers can edit the plans after delivery with the VisioMapEditor Web App.',
            title2: 'Humble UX beginings',
            text2: 'My first big mission at Visioglobe as a Lead designer was to redesign VisioMapEditor and make it “as simple as a box of legos”.  At that time I wasn’t trained in UX design but i was introduced to the methods by an ergonomics engineer who helped us for a couple of days. The first version was very functional but lacking user centered design and a modern UI. More importantly, we had a lot of feedback from users telling us that the training time was too long, it could take weeks. This was the main user and business goal, reduce the time of training by making the app self-learnable and more user friendly. I started by investigating the user needs and we made some proto-personas with feedback from sales and project teams.',
            title3: 'Product design',
            text3: 'The second step was to prioritize the key features of all the the vector softwares that were used by the specialist in order to draw the maps, and the strong technical constraints processes used by our engine. That way we were able to create a roadmap we called VisioMapEditor 2 and start the process with the dev sprints. I organized the UX process by having always some sprints of advance when possible. At that point my task was to re-imagine all the user flows to make them simpler for our less experienced users',
            title4: 'From weeks to days',
            text4: 'The first beta version took us around a year to release, and after internal and external user testing, we were able to put the software in the hands of real customers and the first feedback was excellent, we reached our objective to have the key features learnable in under a week, and the next releases surpassed it as our specialist where only using VisioMapEditor to deliver the maps.',
          },

          {
            title: 'My Visioglobe',
            chip1: 'UX design',
            chip2: 'UI design',
            chip3: 'User Research',
            chip4: 'User testing',
            coverimg1: '../Img/mapeditor2.png',
            img1: '../Img/mapeditor1.7.png',
            captionimg1: 'VisioMapEditor first version',
            img2: '../Img/vme03.jpg',
            captionimg2: 'Sketches with the dev team',
            img3: '../Img/mapeditor2.png',
            captionimg3: 'VisioMapEditor 2',
            subtitle: 'Designing a product Portal',
            context1: 'Lead designer (Ux & Front dev)',
            context2: '2015-2018',
            context3: 'www.visioglobe.com',
            context4: 'Advertise new products and ease support',
            context5: 'Added sales and improved communication',
            title1: 'Optimise communication',
            text1: 'After the success of VisioMapEditor 2 and the mobile map engine thanks to steady sales of licenses, Visioglobe leadership started to create new products by realising some POCs in order to test the markets. Some were fast successes so they were put to production and used by our customers.',
            title2: 'Reducing training time.',
            text2: 'One of the main issues was that all the products were independent from each other, developed as self reliant entities. Each product needed different sales pitch, technical support, user profiles, etc … As this strategy was not sustainable for the long run, we opted to create a product suite accessible via a portal and have all the products be some optional part of a whole solution. The main goal was to make the new products and features self-marketed and self-served for recurring users and to let them know about the new features and new products of the suite.',
            title3: 'Product design',
            text3: 'Using our existing user persona, I started to devise some user flows and after a big survey of all kinds of product hubs, we had to choose a way of making the products connected : by user projects or by Visioglobe’s products. We chose the project as the main entry point as it was our users main goal, to implement a project in their app. After a round of wireframes we settled on a solution, tested it and started implementing, using VueJS as a new UI framework.',
            title4: 'Title 2',
            text4: 'The resulting portal my.visioglobe united all of Visioglobe’s products, enabled the user to see directly the other features of the solution and added key features of support directly in the app, using less and less email communication.',
          },

          {
            title: 'Wynd Picking',
            chip1: 'UX design',
            chip2: 'UI design',
            chip3: 'User Research',
            chip4: 'User testing',
            coverimg1: '../Img/mapeditor2.png',
            img1: '../Img/mapeditor1.7.png',
            captionimg1: 'VisioMapEditor first version',
            img2: '../Img/vme03.jpg',
            captionimg2: 'Sketches with the dev team',
            img3: '../Img/mapeditor2.png',
            captionimg3: 'VisioMapEditor 2',
            subtitle: 'A supply chain business app',
            context1: 'UX designer',
            context2: '2018',
            context3: 'www.wynd.com',
            context4: 'Make pickers walk less than 15km daily',
            context5: 'Simpler solution overall',
            title1: 'Exponential growth',
            text1: 'Wynd is a french tech company distributing a SAAS solution for Omnichannel retail commerce. The company grew exponentially in the years 2017 and 2018. I joined the team as a UX designer in charge of product design in a feature team, it was part of my internship at Gobelin’s school. My team was in charge of the “Picking” product, a solution for click and collect order managing for big retail companies.',
            title2: 'Picking',
            text2: 'We first created the product for one of France’s biggest retailer that already had a solution that was developed “in-house” over the course of 10 years, but was starting to like like a labyrinth system and was using dated hardware.',
            title3: 'Product design',
            text3: 'This was a perfect scenario as we had a solid use-case, hundreds of users and great problems to face. We started by visiting various hypermarkets from that retailer, interviewing and shadowing users, in order to fully understand their goals and struggles. That way we where able to create personas and map out the entire flow of the solution, from the customer order to the delivery.',
            title4: 'Title 2',
            text4: 'The resulting portal my.visioglobe united all of Visioglobes products and this way customers were able to choose their products and see  .',
          },

          {
            title: 'Rowenta',
            chip1: 'UX design',
            chip2: 'UI design',
            chip3: 'User Research',
            chip4: 'User testing',
            coverimg1: '../Img/mapeditor2.png',
            img1: '../Img/mapeditor1.7.png',
            captionimg1: 'VisioMapEditor first version',
            img2: '../Img/vme03.jpg',
            captionimg2: 'Sketches with the dev team',
            img3: '../Img/mapeditor2.png',
            captionimg3: 'VisioMapEditor 2',
            subtitle: 'A supply chain business app',
            context1: 'UX designer',
            context2: '2018',
            context3: 'www.wynd.com',
            context4: 'Make pickers walk less than 15km daily',
            context5: 'Simpler solution overall',
            title1: 'Exponential growth',
            text1: 'Wynd is a french tech company distributing a SAAS solution for Omnichannel retail commerce. The company grew exponentially in the years 2017 and 2018. I joined the team as a UX designer in charge of product design in a feature team, it was part of my internship at Gobelin’s school. My team was in charge of the “Picking” product, a solution for click and collect order managing for big retail companies.',
            title2: 'Picking',
            text2: 'We first created the product for one of France’s biggest retailer that already had a solution that was developed “in-house” over the course of 10 years, but was starting to like like a labyrinth system and was using dated hardware.',
            title3: 'Product design',
            text3: 'This was a perfect scenario as we had a solid use-case, hundreds of users and great problems to face. We started by visiting various hypermarkets from that retailer, interviewing and shadowing users, in order to fully understand their goals and struggles. That way we where able to create personas and map out the entire flow of the solution, from the customer order to the delivery.',
            title4: 'Title 2',
            text4: 'The resulting portal my.visioglobe united all of Visioglobes products and this way customers were able to choose their products and see  .',
          },

          {
            title: 'Gatoreviews',
            chip1: 'UX design',
            chip2: 'UI design',
            chip3: 'User Research',
            chip4: 'User testing',
            coverimg1: '../Img/mapeditor2.png',
            img1: '../Img/mapeditor1.7.png',
            captionimg1: 'VisioMapEditor first version',
            img2: '../Img/vme03.jpg',
            captionimg2: 'Sketches with the dev team',
            img3: '../Img/mapeditor2.png',
            captionimg3: 'VisioMapEditor 2',
            subtitle: 'A supply chain business app',
            context1: 'UX designer',
            context2: '2018',
            context3: 'www.wynd.com',
            context4: 'Make pickers walk less than 15km daily',
            context5: 'Simpler solution overall',
            title1: 'Exponential growth',
            text1: 'Wynd is a french tech company distributing a SAAS solution for Omnichannel retail commerce. The company grew exponentially in the years 2017 and 2018. I joined the team as a UX designer in charge of product design in a feature team, it was part of my internship at Gobelin’s school. My team was in charge of the “Picking” product, a solution for click and collect order managing for big retail companies.',
            title2: 'Picking',
            text2: 'We first created the product for one of France’s biggest retailer that already had a solution that was developed “in-house” over the course of 10 years, but was starting to like like a labyrinth system and was using dated hardware.',
            title3: 'Product design',
            text3: 'This was a perfect scenario as we had a solid use-case, hundreds of users and great problems to face. We started by visiting various hypermarkets from that retailer, interviewing and shadowing users, in order to fully understand their goals and struggles. That way we where able to create personas and map out the entire flow of the solution, from the customer order to the delivery.',
            title4: 'Title 2',
            text4: 'The resulting portal my.visioglobe united all of Visioglobes products and this way customers were able to choose their products and see  .',
          },
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
              title: 'Product Designer - 2014',
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
    },
    mounted() {
      this.projects.forEach((project, i) => {
        console.log("🚀 ~ file: HelloWorld.vue ~ line 460 ~ this.projects.forEach ~ project", project)
        this.dialog[`project${i}`] = false
      });
    }
  }
  
</script>
