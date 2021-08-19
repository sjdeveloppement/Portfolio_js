<template>
  <v-app>
    <div id="allApp">
      <video autoplay loop muted id="bg-video">
        <source src="../assets/Particle.mp4" type="video/mp4" />
      </video>
      <v-card elevation="15" class="card-portfolio ma-6">
        <v-card-title v-if="$vuetify.breakpoint.smAndUp" class="card-title"><h1>WEB DEVELOPER</h1></v-card-title>
        <v-card-title v-if="$vuetify.breakpoint.xsOnly" class="card-title white--text"><h1 style="font-size: 16px; text-align:center;">JAHÂN SERRA <br> WEB DEVELOPER</h1></v-card-title>

        <v-navigation-drawer
          v-if="$vuetify.breakpoint.lgAndUp"
          permanent
          expand-on-hover
          id="menu"
        >
          <v-list>
            <v-list-item class="px-2">
              <v-list-item-avatar id="avatar" >
                <v-img src="../assets/photojahan.jpg"></v-img>
              </v-list-item-avatar>
            </v-list-item>

            <v-list-item >
              <v-list-item-content>
                <v-list-item-title class="text-h6">
                  Jahân Serra
                </v-list-item-title>
                <v-list-item-subtitle>SJ</v-list-item-subtitle>
              </v-list-item-content>
            </v-list-item>
          </v-list>

          <v-divider></v-divider>

          <v-list nav dense>
            <v-list-item link>
              <v-list-item-icon>
                <v-icon>mdi-folder</v-icon>
              </v-list-item-icon>
              <v-list-item-title
                ><a style="color: black" href="/#project"
                  >My Project</a
                ></v-list-item-title
              >
            </v-list-item>
            <v-list-item link>
              <v-list-item-icon>
                <v-icon>mdi-account-multiple</v-icon>
              </v-list-item-icon>
              <v-list-item-title
                ><a style="color: black" href="/#contact"
                  >Contact</a
                ></v-list-item-title
              >
            </v-list-item>
          </v-list>
        </v-navigation-drawer>
        <!-- chips -->
        <template
          ><div class="text-center chips">
            <v-chip
              v-if="$vuetify.breakpoint.smAndUp"
              class="ma-2 chips-lays"
              color="grey darken-4"
              outlined
            >
              <v-icon left> mdi-wrench </v-icon>
              Coding
            </v-chip>
            <v-chip
              v-if="$vuetify.breakpoint.xsOnly"
              class="ma-2 chips-lays"
              color="white darken-4"
              outlined
            >
              <v-icon left> mdi-wrench </v-icon>
              Coding
            </v-chip>
            <v-chip v-if="$vuetify.breakpoint.smAndUp" class="ma-2 chips-lays" color="grey darken-4" outlined>
              <v-icon left> mdi-wrench </v-icon>
              Design
            </v-chip>
            <v-chip v-if="$vuetify.breakpoint.xsOnly" class="ma-2 chips-lays" color="white darken-4" outlined>
              <v-icon left> mdi-wrench </v-icon>
              Design
            </v-chip>
            <v-chip v-if="$vuetify.breakpoint.smAndUp" class="ma-2 chips-lays" color="grey darken-4" outlined>
              <v-icon left> mdi-fire </v-icon>
              SEO
            </v-chip>
            <v-chip v-if="$vuetify.breakpoint.xsOnly" class="ma-2 chips-lays" color="white darken-4" outlined>
              <v-icon left> mdi-fire </v-icon>
              SEO
            </v-chip>
            <v-chip v-if="$vuetify.breakpoint.smAndUp" class="ma-2 chips-lays" color="grey darken-4" outlined>
              <v-icon left> mdi-account-outline </v-icon>
              Teamwork
            </v-chip>
            <v-chip v-if="$vuetify.breakpoint.xsOnly" class="ma-2 chips-lays" color="white darken-4" outlined>
              <v-icon left> mdi-account-outline </v-icon>
              Teamwork
            </v-chip>
          </div></template
        >
        <!-- intro subtitle card -->
        <v-card-subtitle class="card-subtitle"
          >Junior fullstack Web Developper with expericence in<br />
          developing interfaces for web app, eCommerce and database sql and
          noSql. <br />
          Knowledge in SEO and Graphic design.
        </v-card-subtitle>
        <!-- test grid -->

        <v-row v-if="$vuetify.breakpoint.smAndUp" id="project">
          <v-col
            v-for="(asset, index) in assets"
            :key="index"
            class="d-flex child-flex"
            cols="4"
          >
            <v-hover v-slot="{ hover }">
              <a :href="asset.url">
                <v-img
                  :src="asset.src"
                  aspect-ratio="1"
                  class="grey lighten-2 grid-img"
                  @click="checkActive(asset, index)"
                >
                  <v-btn
                    v-for="(icon, index) in icons"
                    :key="index"
                    :class="{ 'show-btns': hover }"
                    :color="transparent"
                    icon
                    ><v-icon
                      :class="{ 'show-btns': hover }"
                      :color="transparent"
                      @click="checkActive(icon, index)"
                    >
                      {{ icon }}
                    </v-icon></v-btn
                  >
                  <h3 v-if="$vuetify.breakpoint.mdAndUp" v-html="asset.title" id="project_titles"></h3>
                  <div v-if="hover" id="icon-language">
                    <v-icon v-html="asset.language[0]"></v-icon
                    ><v-icon v-html="asset.language[1]"></v-icon
                    ><v-icon v-html="asset.language[2]"></v-icon
                    ><v-icon v-html="asset.language[3]"></v-icon>
                    <v-icon v-html="asset.language[4]"></v-icon>
                  </div> </v-img
              ></a>
            </v-hover>
          </v-col>
        </v-row>
        <!-- grille sous mobile -->
         <v-row v-if="$vuetify.breakpoint.xsOnly" id="project">
          <v-col
            v-for="(asset, index) in assets"
            :key="index"
            class="d-flex child-flex"
            cols="12"
          >
            <v-hover v-slot="{ hover }">
              <a :href="asset.url">
                <v-img
                  :src="asset.src"
                  aspect-ratio="1"
                  class="grey lighten-2 grid-img"
                  @click="checkActive(asset, index)"
                >
                  <v-btn
                    v-for="(icon, index) in icons"
                    :key="index"
                    :class="{ 'show-btns': hover }"
                    :color="transparent"
                    icon
                    ><v-icon
                      :class="{ 'show-btns': hover }"
                      :color="transparent"
                      @click="checkActive(icon, index)"
                    >
                      {{ icon }}
                    </v-icon></v-btn
                  >
                  <h3 v-if="$vuetify.breakpoint.mdAndUp" v-html="asset.title" id="project_titles"></h3>
                  <div v-if="hover" id="icon-language">
                    <v-icon v-html="asset.language[0]"></v-icon
                    ><v-icon v-html="asset.language[1]"></v-icon
                    ><v-icon v-html="asset.language[2]"></v-icon
                    ><v-icon v-html="asset.language[3]"></v-icon>
                    <v-icon v-html="asset.language[4]"></v-icon>
                  </div> </v-img
              ></a>
            </v-hover>
          </v-col>
        </v-row>
        <!-- fin test grid -->
      </v-card>
      <!-- Contact -->
      <v-row justify="space-around" id="contact">
        <v-col cols="auto">
          <v-dialog transition="dialog-top-transition" max-width="600">
            <template v-slot:activator="{ on, attrs }">
              <v-btn color="#fb6d45" v-bind="attrs" v-on="on">Contact</v-btn>
            </template>
            <template v-slot:default="dialog">
              <v-card>
                <v-toolbar color="#fb6d45" dark
                  >Let's talk about your project</v-toolbar
                >
                <v-card-text>
                  <div class="pa-6">
                    <v-icon x-large>mdi-email</v-icon
                    ><a href="mailto:jahan.serra@gmail.com" style="color: grey">
                      jahan.serra@gmail.com</a
                    >
                  </div>
                  <div class="pa-6">
                    <a
                      style="color: grey"
                      href="https://www.linkedin.com/in/jahan-serra-a58152125/"
                      ><i class="fab fa-3x fa-linkedin"></i> Linkedin</a
                    >
                  </div>
                  <div class="pa-6">
                    <a
                      style="color: grey"
                      href="https://github.com/sjdeveloppement"
                      ><i class="fab fa-3x fa-github"></i>Github</a
                    >
                  </div>
                </v-card-text>
                <v-card-actions class="justify-end">
                  <v-btn text @click="dialog.value = false">Close</v-btn>
                </v-card-actions>
              </v-card>
            </template>
          </v-dialog>
        </v-col>
      </v-row>
      <!-- fin contact -->
    </div>
  </v-app>
</template>
<script>
export default {
  name: "Portfolio",
  data() {
    return {
      indexClicked: undefined,
      selectedItem: null,
      transparent: "rgba(255, 255, 255, 0)",
      icons: ["mdi-eye"],
      assets: [
        {
          id: 1,
          title: "Groupomania media social d'entreprise",
          src: require("../assets/logo_groupomania.png"),
          url: "https://mygroupomania.web.app/sign-in",
          language: [
            "mdi-vuejs",
            "mdi-vuetify",
            "fab fa-html5",
            "fab fa-css3-alt",
            "fab fa-node-js",
          ],
        },
        {
          id: 2,
          title:
            "So pekocko / piquante l'application qui note vos sauces aux piments préférées !",
          src: require("../assets/Sopekocko.gif"),
          url: "https://github.com/sjdeveloppement/backend",
          language: ["fab fa-node-js"],
        },
        {
          id: 3,
          title: "Orinoco site e-commerce",
          src: require("../assets/orinocam.jpg"),
          url: "https://sjdeveloppement.github.io/jahanSerra_5_09032021/index.html",
          language: ["fab fa-html5", "fab fa-css3-alt", "fab fa-js"],
        },
        {
          id: 4,
          title: "La chouette agence  refonte d'un site vitrine",
          src: require("../assets/chouetteAgence.svg"),
          url: "https://sjdeveloppement.github.io/jahanSerra_4_03032021/",
          language: ["fab fa-html5", "fab fa-css3-alt"],
        },
        {
          id: 5,
          title: "Ohmyfood reservez le menu qui vous convient",
          src: require("../assets/ohmyfood@2x.svg"),
          url: "https://sjdeveloppement.github.io/jahanSerra_3_23022021/",
          language: ["fab fa-html5", "fab fa-css3-alt"],
        },
        {
          id: 6,
          title: "Reservia site vitrine",
          src: require("../assets/Reservia.svg"),
          url: "https://sjdeveloppement.github.io/JahanSerra_2_06022020/",
          language: ["fab fa-html5", "fab fa-css3-alt"],
        },
        {
          id: 7,
          title: "SJdeveloppement site vitrine",
          src: require("../assets/Logo_Sjdevsvg.svg"),
          url: "https://sjdeveloppement.com/",
          language: ["fab fa-wordpress"],
        },
        {
          id: 8,
          title: "Hérault Sport maquette interactive site vitrine",
          src: require("../assets/Herault_Sport_logo.svg"),
          url: "https://jahan.sereneorpatrimoine.fr/herault-sport",
          language: ["fab fa-wordpress"],
        },
        {
          id: 9,
          title: "Ancien portfolio",
          src: require("../assets/jahan.jpg"),
          url: "http://jahan.serra.free.fr/",
          language: ["fab fa-html5", "fab fa-css3-alt"],
        },
      ],
    };
  },
  methods: {
    checkActive(asset, index) {
      this.indexClicked = index;
      this.selectedasset = asset;
      //console.log(this.selectedasset.url);
    },
    goToProject() {
      window.location(this.selectedasset.url);
    },
  },
};
</script>
<style scoped>
.card-portfolio {
  background: rgb(69, 54, 77);
  background: linear-gradient(
    0deg,
    rgba(69, 54, 77, 0.9444152661064426) 0%,
    rgba(84, 58, 76, 1) 12%,
    rgba(123, 70, 74, 1) 47%,
    rgba(252, 109, 69, 0.7494572829131652) 100%
  );
}

.card-title {
  position: absolute;
  left: 3%;
}
#menu {
  position: relative;
  z-index: 1;
}
.chips {
  position: absolute;
  margin-top: -11%;
  margin-left: 4%;
}
.chips-lays {
  box-shadow: 1px 1px 1px 0px #000000;
}
.grid-img {
  box-shadow: 3px 3px 10px 3px #000000;
  opacity: 0.8;
}
.grid-img:hover {
  opacity: 1;
  cursor: pointer;
  text-shadow: 2px 1px 2px #000000;
  font-size: 18px;
}

a {
  text-decoration: none;
}
.show-btns {
  color: rgba(252, 109, 69, 0.7494572829131652) !important;
}
.card-subtitle {
  font-size: larger;
  margin-left: 50px;
  margin-top: -97px;
  position: relative;
  z-index: 0;
  font-style: oblique;
}
#project_titles {
  color: #fc6c44;
  text-align: center;
  margin-top: 20px;
}
#icon-language {
  text-shadow: none;
  text-align: center;
  margin-top: 65%;
}
#bg-video {
  position: fixed;
  z-index: 0;
}
#avatar:hover{
  transform: scale(1.6) rotate(360deg) translateX(50%);
  transition-duration: 1s ;
  transition-timing-function: cubic-bezier(.29, 0.50, 0.15 , 0.68);
  box-shadow: 2px 2px 3px#000000;
  cursor: crosshair ;
  
}
@media (min-aspect-ratio: 16/9) {
  #bg-video {
    width: 100%;
    height: auto;
  }
}
@media (max-aspect-ratio: 16/9) {
  #bg-video {
    width: auto;
    height: 100%;
  }
}
/* Responsive mobile*/
@media (max-width: 767px) {
  #bg-video {
    display: none;
  }
  body {
    background-image: url("../assets/photojahan.jpg");
    background-size: cover;
  }
  h1 {
    margin-left: 50px;
    font-size: 22px;
  }
  .card-title {
    position: relative;
    margin-bottom: 15px;
  }
  .card-subtitle {
    margin-top: 60px;
    color: antiquewhite !important;
  }
  #project{
    font-size: 8px;
  }
  #allApp {
    background-color: rgba(252, 109, 69, 0.7494572829131652);
  }
}
@media (min-width: 768px) and (max-width: 1024px){
  h1 {
    margin-left: 50px;
    font-size: 22px;
    margin-top:30px
  }
  .card-title {
    position: relative;
    margin-bottom: 10px;
  }
  .card-subtitle {
    margin-top: 5px;
    color: antiquewhite !important;
  }
  #project{
    font-size: 18px;
  }
  .chips {
  position: absolute;
  margin-top: -4%;
  margin-left: 4%;
}
}
</style>