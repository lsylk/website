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
        title: 'iManage',
        subTitle: 'Collaborate and Manage all your Projects!',
        description: 'Fun Management',
        img: 'https://www.youtube.com/embed/qJwtnwHQCZQ',
        alt: 'Manager',
        githubUrl: '',
        techStack: ['Javascript', 'Express', 'MongoDB', 'Ava', 'VueJS', 'Docker'],
        isVideo: true,
        status: 'inProgress',
      },
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
          // 'HTML5',
          // 'CSS',
        ],
        status: 'old',
      },
      // {
      //   title: 'Milky',
      //   subTitle: "Come play with me! I'm super cute",
      //   description: 'Best dog ever!',
      //   img: 'https://www.youtube.com/embed/qJwtnwHQCZQ',
      //   alt: 'Video of samoyed',
      //   githubUrl: '',
      //   techStack: [],
      //   isVideo: true,
      //   status: 'new',
      // },

      // { title: 'Title 3', description: 'Description ....', img: '', githubUrl: '', techStack: [] },
      // { title: 'Title 4', description: 'Description ....', img: '', githubUrl: '', techStack: [] },
      // { title: 'Title 5', description: 'Description ....', img: '', githubUrl: '', techStack: [] },
      // { title: 'Title 6', description: 'Description ....', img: '', githubUrl: '', techStack: [] },
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
  justify-content: center;
  // justify-content: flex-start;
  align-content: center;
  flex-wrap: wrap;

  @media (min-width: 100px) and (max-width: 813px) {
    justify-content: center;
    flex-direction: column;
  }
}
</style>
