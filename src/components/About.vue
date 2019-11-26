<template>
  <div class="page-container">
    <div class="split left">
      <div class="centered">
        <img src="./../assets/logoSignatureTransparent.png" />
        <p>
          I am a Front-End Engineer, who has almost 2 years of experience. I am passionate about art and science, and I
          think coding is a great combination of both. With simple and elegant blocks of code, one can produce practical
          and appealing programs for users. I have a growth mindset, and I constantly learn and seek new challenges.
        </p>
        <p>
          My strengths lie within Javascript and AngularJS, and I’m working on deepening my knowledge in Typescript,
          Vue, React and Redux. I had the opportunity to work with and learn from very knowledgeable senior engineers. I
          enjoy building small projects on the side, and I frequently attend meetups and workshops to gain exposure to
          new technologies and meet new people.
        </p>
      </div>
    </div>

    <div class="split right">
      <img
        src="https://images.unsplash.com/photo-1556804599-f7d0c84b61b8?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1000&q=80"
        alt="Avatar man"
      />
    </div>
  </div>
</template>

<script>
export default {
  name: 'About',
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
  overflow: hidden;
  padding-top: 20px;

  @media (min-width: 100px) and (max-width: 1200px) {
    width: 100%;
  }
}

/* Control the left side */
.left {
  left: 0;
}

/* Control the right side */
.right {
  width: 45%;
  right: 0;
  @media (min-width: 401px) and (max-width: 1200px) {
    height: 33%;
    width: 100%;
    left: 32px;
  }

  @media (max-width: 400px) {
    height: 0%;
    width: 0%;
  }
}

.centered {
  position: absolute;
  top: 36%;
  left: 45%;
  transform: translate(-25%, -45%);
  text-align: center;
  @media (min-width: 669px) and (max-width: 1200px) {
    top: 58%;
    left: 35%;
  }

  @media (min-width: 401px) and (max-width: 668px) {
    top: 62%;
    left: 35%;
  }
  @media (max-width: 400px) {
    top: 38%;
    left: 40%;
  }
}

.centered img {
  width: 350px;
  border-radius: 50%;
}
</style>
