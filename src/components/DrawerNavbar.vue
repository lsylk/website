<template>
  <div class="page-container">
    <md-app>
      <md-app-toolbar class="md-primary" md-elevation="0">
        <md-button v-if="!menuVisible" class="md-icon-button" @click="toggleMenu">
          <md-icon>menu</md-icon>
        </md-button>
        <div class="md-title">{{ bannerHeader }}</div>
        <div class="social-media">
          <a title="Contact Me" href="mailto:me@leslye.dev"> <img :src="mailImg"/></a>
          <a title="LinkedIn Profile" href="https://www.linkedin.com/in/lsylk/" target="blank">
            <img :src="linkedInImg" />
          </a>
          <a title="Github Account" href="https://github.com/" target="blank"><img :src="githubImg"/></a>
        </div>
      </md-app-toolbar>

      <md-app-drawer :md-active.sync="menuVisible" :md-persistent="getPersistentType">
        <md-toolbar class="md-transparent" md-elevation="0">
          <div class="md-toolbar-section-end">
            <md-button class="md-icon-button md-dense" @click="toggleMenu">
              <md-icon>keyboard_arrow_left</md-icon>
            </md-button>
          </div>
        </md-toolbar>
        <md-list>
          <md-list-item @click="togglePage('about', 'My Story')">
            <md-icon title="About Me">account_circle</md-icon>
            <span class="md-list-item-text">About</span>
          </md-list-item>

          <md-list-item title="Portfolio" @click="togglePage('portfolio', 'Coding Journey')">
            <md-icon>perm_media</md-icon>
            <span class="md-list-item-text">Portfolio</span>
          </md-list-item>

          <!-- <md-list-item title="Contact Me" @click="togglePage('contact', 'Contact Me')">
            <md-icon>forum</md-icon>
            <span class="md-list-item-text">Contact</span>
          </md-list-item> -->
        </md-list>
      </md-app-drawer>

      <md-app-content>
        <div class="container">
          <About v-if="page === 'about'" />
          <Portfolio v-if="page === 'portfolio'" />
          <!-- <Contact v-if="page === 'contact'" /> -->
        </div>
      </md-app-content>
    </md-app>
  </div>
</template>

<script>
import mailImg from './../assets/socialMedia/mail-white-64.png';
import linkedInImg from './../assets/socialMedia/linkedin-white-32.png';
import githubImg from './../assets/socialMedia/github-white-32.png';
import About from './About';
import Portfolio from './Portfolio';
// import Contact from './Contact';

export default {
  name: 'DrawerNavbar',
  components: {
    About,
    Portfolio,
    // Contact,
  },
  data: () => ({
    mailImg,
    linkedInImg,
    githubImg,
    menuVisible: false,
    page: 'about',
    bannerHeader: 'My Story',
  }),
  computed: {
    getPersistentType() {
      return window.screen.width > 414 ? 'mini' : 'full';
    },
  },
  methods: {
    toggleMenu() {
      this.menuVisible = !this.menuVisible;
    },
    togglePage(page, bannerHeader) {
      this.page = page;
      this.bannerHeader = bannerHeader;
    },
  },
};
</script>

<style lang="scss" scoped>
.md-app {
  min-height: 1000px;
  border: 1px solid rgba(#000, 0.12);
}

.md-app-toolbar {
  background-color: #8d6aea !important;
  display: flex;
  justify-content: space-between;

  .social-media {
    a {
      color: inherit;
      text-decoration: none;
    }
    img {
      height: 28px;
      padding-right: 4px;
    }
  }
}

.md-drawer {
  width: 160px;
  max-width: calc(100vw - 125px);
}
</style>
