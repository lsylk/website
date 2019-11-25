<template>
  <div class="page-container">
    <div class="split left">
      <div class="centered">
        <!-- <img src="img_avatar2.png" alt="Avatar woman" /> -->
        <img src="./../assets/logoSignatureTransparent.png" />
        <h2></h2>
        <p>Some text.</p>
      </div>
    </div>

    <div class="split right">
      <!-- <div class="centered"> -->
      <img
        src="https://images.unsplash.com/photo-1556804599-f7d0c84b61b8?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1000&q=80"
        alt="Avatar man"
      />
      <!-- <img
        src="https://images.unsplash.com/photo-1516373829531-29d21ac7f9d6?ixlib=rb-1.2.1&amp;ixid=eyJhcHBfaWQiOjEyMDd9&amp;auto=format&amp;fit=crop&amp;w=1000&amp;q=80"
        alt="person holding clear crystal ball"
      /> -->
      <!-- <h2>John Doe</h2>
        <p>Some text here too.</p>
      </div> -->
    </div>
  </div>
</template>

<script>
export default {
  name: 'About',
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
/* Split the screen in half */
.split {
  height: 100%;
  width: 50%;
  position: fixed;
  z-index: 1;
  top: 0;
  overflow-x: hidden;
  padding-top: 20px;
}

/* Control the left side */
.left {
  left: 0;
  //   background-color: wheat;
}

/* Control the right side */
.right {
  width: 45% !important;
  right: 0;
  background-color: crimson;
}

/* If you want the content centered horizontally and vertically */
.centered {
  position: absolute;
  top: 25%;
  left: 45%;
  transform: translate(-25%, -45%);
  text-align: center;
}

/* Style the image inside the centered container, if needed */
.centered img {
  width: 350px;
  border-radius: 50%;
}
</style>
