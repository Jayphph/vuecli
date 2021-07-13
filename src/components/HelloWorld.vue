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
        <div class="py-16"></div>
        <v-container class="text-center">
          <h1>Hi ! I'm JF</h1>
          <v-responsive class="mx-auto mb-8">
            <p class="mb-6">Product designer, project manager and UX teacher</p>
            <p>I am an accomplished product designer with more than 13 years of experience in the digital industry and 6 years as a UX designer. I love building business applications with great user value, for the supply chain, smart buildings, IOT and others ...</p>
          </v-responsive>
        </v-container>
        <div class="py-12 d-none d-sm-block"></div>
        <div class="py-4 d-flex d-sm-none"></div>
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
        <div class="py-16 d-none d-sm-block"></div>
        <div class="py-4 d-flex d-sm-none"></div>
      </section>
      <section>
        <v-container class="work" id="work">
          <div class="py-4"></div>  
          <h2 class="text-center">Work</h2>
          <p class="text-center">Selected works from 2014-2020</p>
          <v-carousel 
            :cycle="cycle"
            :show-arrows="false"
            hide-delimiter-background
            delimiter-icon="mdi-circle-medium"
          >
              <v-carousel-item :key="i" v-for="(project, i) in projects">
                  <v-dialog v-model="dialog[`project${i}`]" max-width="926" scrollable :key="`dialog-${i}`">                
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
                      <v-card id="project" class="project_card" @click="closeDialog(i)" :key="`card-${i}`">
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
                            <p class="dimmed context"><span class="context_type" v-text="project.context1"></span></p>
                            <p class="dimmed context"><a class="context_type" v-text="project.context2" :href="project.contexturl"></a></p>
                            <div class="py-4"></div>
                            <h5 v-text="project.title1"></h5>
                            <p v-text="project.text1"></p>
                            <p v-text="project.text2"></p>
                            <p v-text="project.text3"></p>
                            <div class="py-4"></div>
                          </v-container>
                          <v-img class="card_content" height="auto" :src="project.img1"></v-img>
                          <p class="imgcaption"><span v-text="project.captionimg1"></span></p>
                          <div class="py-4"></div>
                          <v-img class="card_content" height="auto" :src="project.img2"></v-img>
                          <p class="imgcaption"><span v-text="project.captionimg2"></span></p>
                          <div class="py-4"></div>
                          <v-img class="card_content" height="auto" :src="project.img3"></v-img>
                          <p class="imgcaption"><span v-text="project.captionimg3"></span></p>
                        </v-card-text>
                      </v-card>
                  </v-dialog>
              </v-carousel-item>
          </v-carousel>
        </v-container>
      </section>
      <section>
        <v-container class="experience_container" id="experience">
          <div class="py-4"></div>  
          <h2 class="py-6 mb-6 text-center">Experience</h2>
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
                    <v-img class="card_content" :src="experience.src"></v-img>
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
        </v-container>
        <div class="py-6 d-none d-sm-block"></div>
        <div class="py-4 d-flex d-sm-none"></div>
      </section>
      <section>
        <v-container id="about">
          <div class="py-4" id="top"></div>
          <h2 class="my-3 text-center">About me</h2>
          <v-row class="mx-auto mb-8">
            <v-col cols="12" sm="7">
              <h5>Senior UX designer and teacher</h5>
              <ul class="mb-6">
                <li>Lean UX design methods</li>
                <li>SAAS Product & service oriented</li>
                <li>UX teaching & mentoring</li>
              </ul>
              <h5>Project manager</h5>
              <ul class="mb-6">
                <li>Strong experience in Agile projects</li>
                <li>Experience in team management</li>
                <li>Trued communication skills</li>
              </ul>
              <h5>UI developer</h5>
              <ul class="mb-6">
                <li>I can integrate Front-end web technologies</li>
                <li>I'm familiar with VueJs, Github and Netlify</li>
                <li>Like this website</li>
              </ul>
            </v-col>
            <v-col cols="12" sm="5">
              <v-img height="250" :src="me"></v-img>
              <div class="py-6"></div>
              <div class="contact">
                <v-btn class="link_button" href="https://vuetifyjs.com">
                  <span>
                    Call me: +33 6 98 63 39
                  </span>
                </v-btn>
                <div class="py-1"></div>
                <v-btn class="link_button" href="mailto:jfphaner.pro@gmail.com">
                  <span>
                    Send me an email 
                  </span>
                </v-btn>
                <div class="py-1"></div>
                <v-btn class="link_button" href="../Files/JFPHANER_CV2021.pdf" download>
                  <span>
                    Download my resume
                  </span>
                </v-btn>
                <div class="py-1"></div>
                <v-btn class="link_button" href="https://www.linkedin.com/in/jf-phaner-37b1b516/">
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
        me: '../Img/Me.png',
        projects: [
          {
            title: 'GTR suite',
            chip1: 'UX design',
            chip2: 'UI design',
            chip3: 'User Research',
            chip4: 'User testing',
            coverimg1: '../Img/Gtr_01.png',
            img1: '../Img/Gtr_02.png',
            captionimg1: 'Story mapping is an important tool in order to get a quick consensus with the client and produce user flow wireframes fast.',
            img2: '../Img/Gtr_03.png',
            captionimg2: 'Creating a design system was one of the deliverable created in order to help the dev team integrate screens faster.',
            img3: '../Img/Gtr_04.png',
            captionimg3: 'One of the objective was to design a fully responsive product, in order to let users and business teams be totally free on the go.',
            subtitle: 'Creating a self serving product',
            context1: 'Freelance product designer - 2020',
            context2: 'www.gatoreviews.com',
            contexturl: 'https://www.gtrsuite.com/',
            title1: 'Gain: a modern & complete solution',
            text1: 'GTR suite is a French SAAS startup situated in the alps. Created in 2019, their main product is an online reputation and influence tool for big retail chains.',
            text2: 'As my first big mission as an independent consultant, i was asked to create a fully self served app in order for direct clients to create marketing campaigns without the help of business developers.',
            text3: 'My work consisted of making specifications, designing user flow and wireframing the basic principles of the app in order for the UI devs to create the product.',
          },
          {
            title: 'Rowenta',
            chip1: 'UX design',
            chip2: 'UI design',
            chip3: 'User Research',
            chip4: 'User testing',
            coverimg1: '../Img/Row_01.png',
            img1: '../Img/Row_02.png',
            captionimg1: 'Resulting',
            img2: '',
            captionimg2: '',
            img3: '',
            captionimg3: '',
            subtitle: 'From online catalog to a D2C platform',
            context1: 'Senior UX designer - 2019',
            context2: 'www.rowenta.fr',
            contexturl: 'https://www.rowenta.fr/',
            title1: 'Gain: Creating a brand experience',
            text1: 'Rowenta, a brand of one of France biggest home appliance manufacturer, had always sold their products indirectly through big retail chains such as Darty, Boulanger, Carrefour, etc… One of their main goals was to try and sell directly to their customers in order to create a new way of making revenue and creating a modern brand customer experience.',
            text2: 'This was my main project at Accenture Digital in early 2019, there i discovered new methods of designing by co-creating with an art director. This method made us gain considerable time by sketching our ideas quickly on whiteboard and integrating the brand experience in UX. The project is now live and i left the company to start my freelance adventure before seeing it go in production.',
            text3: ' ',
          },
          {
            title: 'Wynd Picking',
            chip1: 'UX product design',
            chip2: 'User Research',
            chip3: 'User testing',
            coverimg1: '../Img/Wyn_01.png',
            img1: '../Img/Wyn_02.png',
            captionimg1: 'Observing tens of users in their context, getting in their shoes, and doing shadowing and interviewing sessions.',
            img2: '../Img/Wyn_03.png',
            captionimg2: 'Mapping the project: Creating personas and experience maps in order to organize the project with the PO, using a master story mapping document and divising it into smaller story mapping.',
            img3: '../Img/Wyn_04.png',
            captionimg3: 'The resulting back office used today.',
            subtitle: 'A supply chain business app, improving the life of hundreds of users',
            context1: 'UX designer - 2018',
            context2: 'www.wynd.com',
            contexturl: 'https://www.wynd.eu/fr/',
            title1: 'Gain: a Simpler solution overall',
            text1: 'Wynd is a french tech company distributing a SAAS solution for big retail commerce. I joined the team as part of my internship at Gobelin’s school. My feature team was in charge of the “Picking” product, a solution for click and collect order managing for big retail companies.',
            text2: 'We first created the product for one of France’s biggest retailers that already had a “in-house” solution that was starting to like a labyrinth system and was using dated hardware. This was a perfect scenario as we had a solid use-case, hundreds of users and great problems to face. We were able to create personas and map out the entire flow of the solution, from the customer order to the delivery.',
            text3: 'One of the main user goal was to reduce the average distance of 15km travelled on foot by the pickers daily.',
          },
          {
            title: 'My Visioglobe',
            chip1: 'UX design',
            chip2: 'UI design',
            chip3: 'User Research',
            chip4: 'User testing',
            coverimg1: '../Img/Mvg_01.png',
            img1: '../Img/Mvg_02.png',
            captionimg1: 'Visioglobe growing product solution, not all pictured here. A map visualisation and guiding engine, VisioMapEditor, IOT assets management, Key indicators management, and more ...',
            img2: '../Img/Mvg_03.png',
            captionimg2: 'The resulting proposed portal : Because our users process is centered around the project we decided to make it the entry point. That way we were able to design project support features attached to the projects.',
            img3: '../Img/Mvg_04.png',
            captionimg3: 'Resulting UX and UI coherency throughout the whole solution with product and project switching features.',
            subtitle: 'Designing a product Portal',
            context1: 'Lead designer (Ux & Front dev) - 2015-2017',
            context2: 'www.visioglobe.com',
            contexturl: 'https://www.visioglobe.com/',
            title1: 'Gain: Improved communication',
            text1: 'After the success of VisioMapEditor 2 and other products like the mobile map engine, Visioglobe leadership started to create new products by realising some POCs in order to test the markets. Some were fast successes so they were put to production and used by our customers.',
            text2: 'One of the main issues was that all the products were independent from each other, developed as self reliant entities. As this strategy was not sustainable for the long run, we opted to create a product suite accessible via a portal and have all the products be some optional part of a whole solution. The main goal was to make the new products and features self-marketed and self-served for recurring users and to let them know about the new features and new products of the suite.',
            text3: 'The resulting portal my.visioglobe united all of Visioglobe’s products, enabled the user to see directly the other features of the solution and added key features of support directly in the app, using less and less email communication..',
          },
          {
            title: 'VisioMapEditor',
            chip1: 'UX design',
            chip2: 'UI design',
            chip3: 'User Research',
            chip4: 'User testing',
            coverimg1: '../Img/Vme_01.png',
            img1: '../Img/Vme_02.png',
            captionimg1: 'VisioMapEditor first version before my mission, very functionnal and amazing knowing it was developped by only one person.',
            img2: '../Img/Vme_03.jpg',
            captionimg2: 'Practicing co-design sketching sessions with the dev team made us gain considerable time to shape quickly the most complex features',
            img3: '../Img/Vme_04.png',
            captionimg3: 'The resulting interface : VisioMapEditor 2',
            subtitle: 'From a specialist tool to a box of Legos',
            context1: 'Lead designer (Ux & Front dev) - 2014-2015',
            context2: 'www.visioglobe.com',
            contexturl: 'https://www.visioglobe.com/',
            title1: 'Gains : From weeks to days',
            text1: 'Visioglobe offers an indoor guiding SAAS solution for Airports, Malls, Smart cities, etc ... and their customers can edit the plans after delivery with the VisioMapEditor Web App.',
            text2: 'My first big mission at Visioglobe as a Lead designer was to redesign VisioMapEditor and make it “as simple as a box of legos”. We had a lot of feedback from users telling us that the training time was too long, it could take weeks.',
            text3: 'We identified this as our main user and business goal : reduce the time of training by making the app self-learnable and more user friendly. We achieved this goal after a couple of releases, the learning time went from a week to a couple of days, the feedback volume shrunk and our map designers never went back to use another vector drawing tool.',
          },
        ],
        experiences: [
          {
              step: '1',
              src: '../Img/Exp_01.png',
              date: '',
              title: 'Webdesigner - 2007',
              text: 'After completing my Scientific Baccalaureate, i studied Webdesign at Supcrea Grenoble in 2004-2007. I then worked for 5 years as a web and graphic designer, mostly for E-commerce and in an agency in Montreal.',
              companies: 'Companies : Fitness boutique, Sport Aix Trem and Zip communication.',
          },
          {
              step: '2',
              src: '../Img/Exp_02.png',
              date: '',
              title: 'Lead designer - 2013',
              text: 'When i came back to France and i was offered a job as a Lead designer for Visioglobe in Grenoble. Because it was mostly a pure tech company, my responsibilities where to lead design on all the products of the company.',
              companies: 'Companies : Visioglobe',
          },
          {
              step: '3',
              src: '../Img/Exp_03.png',
              date: '',
              title: 'UX Designer - 2015',
              text: 'I started to get interested about UX when in 2013 i worked on a project with an experienced computer ergonomics engineer who mentored me, i then followed courses online on how to implement user centered design in Visioglobe many products. After a couple of years i then went back to school in 2017-2018 in order to obtain the Digital Project Director / UX designer diploma at the Gobelins school in Paris.',
              companies: 'Companies : Visioglobe, Wynd, Accenture.',
          },
          {
              step: '4',
              src: '../Img/Exp_04.png',
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
    },
    methods: {
      closeDialog(index) {
        this.dialog = {
          ...this.dialog,
          [`project${index}`]: false
        }
      }
    }
  }
  
</script>
