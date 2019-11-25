<template>
  <div class="portafolio-grid">
    <div v-for="(item, index) in items" :key="index" class="page-container">
      <ItemCard :item="item" />
    </div>
  </div>
</template>

<script>
import ItemCard from './ItemCard';
import inSkyImg from '../assets/inSky256x160.png';

export default {
  name: 'Portfolio',
  components: {
    ItemCard,
  },
  data: () => ({
    items: [
      {
        title: 'inSky',
        subTitle: 'Book your Flights Now!',
        description:
          'inSky is a user-driven web app that provides the ability for users to find the best flight deals for their travels.',
        img: inSkyImg,
        alt: 'inSky web app that helps users find cheap flights.',
        githubUrl: 'https://github.com/lsylk/Airfare-Project',
        techStack: [
          'QPX Express API',
          'Python',
          'Javascript',
          'AngularJS',
          'Flask',
          'Jinja',
          'Bootstrap',
          'HTML5',
          'CSS',
        ],
      },
      {
        title: 'Milky',
        subTitle: "Come play with me! I'm super cute",
        description: 'Best dog ever!',
        img:
          'https://i.ytimg.com/vi/qJwtnwHQCZQ/hqdefault.jpg?sqp=-oaymwEZCNACELwBSFXyq4qpAwsIARUAAIhCGAFwAQ==&rs=AOn4CLAHiYcuUMqiYW-KVKALcPbZm_7NxA',
        alt: 'Video of samoyed',
        githubUrl: 'https://github.com/lsylk/Airfare-Project',
        techStack: [],
      },
      { title: 'Title 2', description: 'Description ....', img: '', githubUrl: '', techStack: [] },
      { title: 'Title 3', description: 'Description ....', img: '', githubUrl: '', techStack: [] },
      { title: 'Title 4', description: 'Description ....', img: '', githubUrl: '', techStack: [] },
      { title: 'Title 5', description: 'Description ....', img: '', githubUrl: '', techStack: [] },
      { title: 'Title 6', description: 'Description ....', img: '', githubUrl: '', techStack: [] },
    ],
  }),
  methods: {
    // cons() {
    //   console.log('hello', this.testItem);
    // },
  },
};
</script>

<style lang="scss" scoped>
.md-app {
  min-height: 350px;
  border: 1px solid rgba(#000, 0.12);
}

.portafolio-grid {
  display: flex;
  // justify-content: start;
  justify-content: flex-start;
  align-content: center;
  flex-wrap: wrap;

  @media (min-width: 100px) and (max-width: 813px) {
    justify-content: center;
    flex-direction: column;
  }
}
</style>
