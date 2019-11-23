<template>
  <div class="page-container">
    <md-app>
      <md-app-toolbar class="md-primary" md-elevation="0">
        <md-button v-if="!menuVisible" class="md-icon-button" @click="toggleMenu">
          <md-icon>menu</md-icon>
        </md-button>
        <span class="md-title">My Title</span>
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
          <md-list-item>
            <md-icon>account_circle</md-icon>
            <span class="md-list-item-text">About</span>
          </md-list-item>

          <md-list-item>
            <md-icon>perm_media</md-icon>
            <span class="md-list-item-text">Portfolio</span>
          </md-list-item>

          <md-list-item>
            <md-icon>forum</md-icon>
            <span class="md-list-item-text">Contact</span>
          </md-list-item>
        </md-list>
      </md-app-drawer>

      <md-app-content>
        Lorem ipsum dolor sit amet, consectetur adipisicing elit. Error quibusdam, non molestias et! Earum magnam,
        similique, quo recusandae placeat dicta asperiores modi sint ea.
      </md-app-content>
    </md-app>
  </div>
</template>

<script>
export default {
  name: 'DrawerNavbar',
  data: () => ({
    menuVisible: false,
  }),
  methods: {
    toggleMenu() {
      this.menuVisible = !this.menuVisible;
    },
  },
};
</script>

<style lang="scss" scoped>
.md-app {
  min-height: 350px;
  border: 1px solid rgba(#000, 0.12);
}

// Demo purposes only
.md-drawer {
  width: 230px;
  max-width: calc(100vw - 125px);
}
</style>
