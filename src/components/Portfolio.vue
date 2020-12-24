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
import justWatchImg from '../assets/projects/justWatchLogo-256.png';
import olxLogoImg from '../assets/projects/olxLogo-160.png';
import iManageDemo from '../assets/projects/iManageDemo.mp4';

export default {
  name: 'Portfolio',
  components: {
    ItemCard,
  },
  data: () => ({
    items: [
      {
        title: 'OLX Group',
        subTitle: 'A worldwide leading classifieds platform!',
        description: `Currently working on helping people around the world to buy and sell in a transparent, fast and secure way.`,
        img: olxLogoImg,
        alt: 'OLX Group Logo',
        githubUrl: 'https://www.olxgroup.com',
        techStack: ['TypeScript', 'React', 'Storybook', 'Jest', 'Puppeteer', 'Internal tools'],
        status: 'work',
      },
      {
        title: 'JustWatch',
        subTitle: 'World Largest Streaming Guide!',
        description:
          'Worked at JustWatch for 2 years as a Frontend Engineer. JustWatch has 12M monthly active users over mobile and web.',
        img: justWatchImg,
        alt: 'JustWatch Logo',
        githubUrl: 'https://www.justwatch.com/nz',
        techStack: ['Javascript', 'AngularJS', 'VueJS', 'TypeScript', 'Bootstrap', 'Ionic'],
        status: 'work',
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
      {
        title: 'iManage',
        subTitle: 'Collaborate and Manage all your Projects!',
        description:
          'Task, Sprint, and Backlog tracker for agile development projects. It can be used to track progress, record details, comments...',
        // assignee, and task history.
        // It will be able to save data locally and on the server using a database.
        // The implemented APIs are following a RESTful approach.
        // It is built with Javascript, Express, Vue, Mongoose, Material Design, Ava, Jest, Cypress and Docker.',
        img: iManageDemo,
        alt: 'Video of the Task, Sprint, and Backlog tracker for agile development projects',
        githubUrl: 'https://github.com/lsylk/iManage',
        techStack: ['Javascript', 'Express', 'MongoDB', 'Ava', 'VueJS', 'Jest', 'Cypress', 'Docker'],
        isVideo: true,
        status: 'inProgressRelease',
      },
      {
        title: 'Redesign Website',
        subTitle: 'Time for a new look!',
        description: "Redesign customer's personal website with modern frameworks.",
        img: '',
        alt: 'Personal Website by Aaron Elligsen',
        githubUrl: 'https://aaronelligsen.com/',
        techStack: ['Javascript', 'React', 'Jest', 'Cypress'],
        isVideo: true,
        status: 'inProgress',
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
