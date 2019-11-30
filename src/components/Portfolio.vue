<template>
  <div class="portafolio-grid">
    <div v-for="(item, index) in items" :key="index" class="page-container">
      <ItemCard :item="item" />
    </div>
  </div>
</template>

<script>
import ItemCard from './ItemCard';
import inSkyImg from '../assets/projects/inSky256x160.png';

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
        description: '',
        img: '',
        alt: '',
        githubUrl: '',
        techStack: ['Javascript', 'Express', 'MongoDB', 'Ava', 'VueJS', 'Jest', 'Cypress', 'Docker'],
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
        techStack: ['QPX Express API', 'Python', 'Javascript', 'AngularJS', 'Flask', 'Jinja', 'Bootstrap'],
        status: 'old',
      },
    ],
  }),
};
</script>

<style lang="scss" scoped>
.md-app {
  min-height: 350px;
  border: 1px solid rgba(#000, 0.12);
}

.portafolio-grid {
  display: flex;
  justify-content: space-evenly;
  align-content: center;
  flex-wrap: wrap;

  @media (min-width: 100px) and (max-width: 813px) {
    justify-content: center;
    flex-direction: column;
  }
}
</style>
