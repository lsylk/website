<template>
  <div class="page-container">
    <md-app>
      <md-app-toolbar class="md-primary" md-elevation="0">
        <md-button v-if="!menuVisible" class="md-icon-button" @click="toggleMenu">
          <md-icon>menu</md-icon>
        </md-button>
        <div class="md-title">{{ page }}</div>
        <div class="social-media">
          <a title="Contact Me" href="mailto:me@leslye.dev"> <img :src="mailImg"/></a>
          <a title="LinkedIn Profile" href="https://www.linkedin.com/in/lsylk/" target="blank">
            <img :src="linkedInImg" />
          </a>
          <a title="Github Account" href="https://github.com/lsylk" target="blank"><img :src="githubImg"/></a>
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
          <md-list-item @click="togglePage('My Story')">
            <md-icon title="My Story">account_circle</md-icon>
            <span class="md-list-item-text">My Story</span>
          </md-list-item>

          <md-list-item title="Portfolio" @click="togglePage('Portfolio')">
            <md-icon>perm_media</md-icon>
            <span class="md-list-item-text">Portfolio</span>
          </md-list-item>
        </md-list>
      </md-app-drawer>

      <md-app-content>
        <div class="container">
          <About v-if="page === 'My Story'" />
          <Portfolio v-if="page === 'Portfolio'" />
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

export default {
  name: 'DrawerNavbar',
  components: {
    About,
    Portfolio,
  },
  data: () => ({
    mailImg,
    linkedInImg,
    githubImg,
    menuVisible: false,
    page: 'My Story',
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
    togglePage(page) {
      this.page = page;
    },
  },
};
</script>

<style lang="scss" scoped>
.md-app {
  height: 630px;
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

@media (min-width: 600px) {
  .md-app-content {
    border-right: 0px;
  }
}
</style>
