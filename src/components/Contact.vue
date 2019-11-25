<template>
  <div class="page-container">
    <div>
      <md-field>
        <label>Name</label>
        <md-input v-model="name"></md-input>
      </md-field>

      <md-field>
        <label>Email (Required)</label>
        <md-input v-model="email"></md-input>
      </md-field>

      <md-field>
        <label>Message</label>
        <md-textarea v-model="message"></md-textarea>
      </md-field>
    </div>
    <div>
      <md-button class="md-dense md-raised submit">Submit</md-button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Contact',
  //   data: () => ({
  //     menuVisible: false,
  //   }),
  //   methods: {
  //     toggleMenu() {
  //       this.menuVisible = !this.menuVisible;
  //     },
  //   },
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

.submit {
  background-color: #8d69ea !important;
  color: white !important;
}
</style>
