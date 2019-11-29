<template>
  <div class="page-container">
    <div id="leftContent">
      <img id="img1" src="./../assets/logoSignatureTransparent.png" />
      <p>
        I am a Front-End Engineer, who has almost 2 years of experience. I am passionate about art and science, and I
        think coding is a great combination of both. With simple and elegant blocks of code, one can produce practical
        and appealing programs for users. I have a growth mindset, and I constantly learn and seek new challenges.
      </p>
      <p>
        My strengths lie within Javascript and AngularJS, and I’m working on deepening my knowledge in Typescript, Vue,
        React and Redux. I had the opportunity to work with and learn from very knowledgeable senior engineers. I enjoy
        building small projects on the side, and I frequently attend meetups and workshops to gain exposure to new
        technologies and meet new people.
      </p>
    </div>

    <div id="rightContent">
      <img id="img1" src="https://images.unsplash.com/photo-1500964757637-c85e8a162699" alt="Colorful landscape" />
      <img id="img2" src="https://images.unsplash.com/photo-1556139943-4bdca53adf1e" alt="Waves of pastel colors" />
      <img
        id="img3"
        src="https://images.unsplash.com/photo-1532422769059-f95b64af17ad"
        alt="Gray, red, and white mosaic building painting"
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
.page-container {
  display: grid;
  grid-template-areas: 'leftContent rightContent';
  grid-template-columns: 50%;
}

#leftContent {
  grid-area: leftContent;
  padding: 10px;
  img {
    max-height: 335px;
    max-width: 335px;
  }
}

#rightContent {
  grid-area: rightContent;
  display: grid;
  grid-template-areas:
    '.  . img1'
    '. img2 . '
    'img3 . .';
  justify-items: center;
  align-items: center;
}

#img1 {
  grid-area: img1;
}

#img2 {
  grid-area: img2;
}

#img3 {
  grid-area: img3;
}

#img1,
#img2,
#img3 {
  width: 215px;
  height: 215px;
  position: relative;
  overflow: hidden;
  border-radius: 50%;
}

/* Stack the layout on small devices/viewports. */
@media all and (max-width: 1200px) {
  .page-container {
    grid-template-areas:
      'leftContent'
      'rightContent';
    grid-template-rows: auto auto;
    grid-template-columns: auto;
  }

  #rightContent {
    grid-template-areas: 'img1 img2 img3';
    #img1,
    #img2,
    #img3 {
      width: 200px;
      height: 200px;
    }
  }
}

@media all and (max-width: 725px) {
  #rightContent {
    grid-template-areas: 'img1 img2 img3';

    #img1,
    #img2,
    #img3 {
      width: 100px;
      height: 100px;
    }
  }
}
</style>
