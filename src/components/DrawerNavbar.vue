<template>
  <div class="page-container">
    <md-app>
      <md-app-toolbar class="md-primary" md-elevation="0">
        <md-button v-if="!menuVisible" class="md-icon-button" @click="toggleMenu;">
          <md-icon>menu</md-icon>
        </md-button>
        <span class="md-title">{{ bannerHeader }}</span>
      </md-app-toolbar>

      <md-app-drawer :md-active.sync="menuVisible" md-persistent="mini">
        <md-toolbar class="md-transparent" md-elevation="0">
          <span>Navigation</span>

          <div class="md-toolbar-section-end">
            <md-button class="md-icon-button md-dense" @click="toggleMenu">
              <md-icon>keyboard_arrow_left</md-icon>
            </md-button>
          </div>
        </md-toolbar>
        <md-list>
          <md-list-item @click="togglePage('about', 'My Story')">
            <md-icon>account_circle</md-icon>
            <span class="md-list-item-text">About</span>
          </md-list-item>

          <md-list-item @click="togglePage('portfolio', 'Adventurous coding Journey')">
            <md-icon>perm_media</md-icon>
            <span class="md-list-item-text">Portfolio</span>
          </md-list-item>

          <md-list-item @click="togglePage('contact', 'Contact Me')">
            <md-icon>forum</md-icon>
            <span class="md-list-item-text">Contact</span>
          </md-list-item>
        </md-list>
      </md-app-drawer>

      <md-app-content>
        <div class="container">
          <About v-if="page === 'about'" />
          <Portfolio v-if="page === 'portfolio'" />
          <Contact v-if="page === 'contact'" />
        </div>
      </md-app-content>
    </md-app>
  </div>
</template>

<script>
import About from './About';
import Portfolio from './Portfolio';
import Contact from './Contact';

export default {
  name: 'DrawerNavbar',
  components: {
    About,
    Portfolio,
    Contact,
  },
  data: () => ({
    menuVisible: false,
    page: 'about',
    bannerHeader: 'My Story',
  }),
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
}

.md-title {
  align-content: center;
}

// // Demo purposes only
// .md-drawer {
//   width: 230px;
//   max-width: calc(100vw - 125px);
// }
</style>
