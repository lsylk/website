<template>
  <div class="page-container">
    <md-app>
      <md-app-toolbar class="md-dense">
        <div class="md-toolbar-section-start">
          <md-tabs class="md-primary">
            <md-tab id="tab-my-story" md-label="My Story" @click="togglePage('My Story')"></md-tab>
            <md-tab id="tab-portfolio" md-label="Portfolio" @click="togglePage('Portfolio')"></md-tab>
            <md-tab id="tab-blog" md-label="Blog" @click="togglePage('Blog')" md-disabled></md-tab>
          </md-tabs>
        </div>
        <div class="md-toolbar-section-end">
          <div class="social-media">
            <a title="Contact Me" href="mailto:me@leslye.dev"> <img :src="mailImg"/></a>
            <a title="LinkedIn Profile" href="https://www.linkedin.com/in/lsylk/" target="blank">
              <img :src="linkedInImg" />
            </a>
            <a title="Github Account" href="https://github.com/lsylk" target="blank"><img :src="githubImg"/></a>
          </div>
        </div>
      </md-app-toolbar>
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
  name: 'Navbar',
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
.md-app-toolbar {
  background-color: #8d6aea !important;

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

@media (min-width: 600px) {
  .md-app-content {
    border-right: 0px;
  }
}
</style>
