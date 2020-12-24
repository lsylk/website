<template>
  <div class="page-container">
    <div id="leftContent">
      <img id="img1" src="./../assets/about/logoSignatureTransparent.png" />
      <p>{{ p1 }}</p>
      <p>{{ p2 }}</p>
    </div>

    <div id="rightContent">
      <img id="img1" src="./../assets/about/paintedMountains-250.jpeg" alt="Colorful landscape" />
      <img id="img2" src="./../assets/about/colorfulArt-250.jpeg" alt="Waves of pastel colors" />
      <img
        id="img3"
        src="./../assets/about/colorfulGrayBuilding-250.jpeg"
        alt="Gray, red, and white mosaic building painting"
      />
    </div>
  </div>
</template>

<script>
export default {
  name: 'About',
  data: () => ({
    p1,
    p2,
  }),
};

const p1 = `I am a Front-End Engineer, who loves to travel and learn new langauges. I am passionate about art and science, and I
        think coding is a great combination of both. With simple and elegant blocks of code, one can produce practical
        and appealing programs for users. I have a growth mindset, and I constantly learn and seek new challenges.`;
const p2 = `My strengths lie within Javascript and AngularJS, and I’m working on deepening my knowledge in Typescript, Vue,
        React and Redux. I had the opportunity to work with and learn from very knowledgeable senior engineers. I enjoy
        building small projects on the side, and I frequently attend meetups and workshops to gain exposure to new
        technologies and meet new people.`;
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
  p {
    text-align: left;
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
