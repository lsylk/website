<template>
  <md-card>
    <md-card-header>
      <span v-if="item.isNew" class="new-banner">
        New
      </span>
      <div class="md-title">
        {{ item.title }}
        <span class="github-icon">
          <a :href="item.githubUrl" target="blank">
            <img :src="githubImg" alt="Github Repository" />
          </a>
        </span>
      </div>
      <div class="md-subhead">{{ item.subTitle }}</div>
    </md-card-header>

    <md-card-media>
      <img :src="item.img" :alt="item.alt" />
    </md-card-media>

    <hr />

    <md-card-content>
      {{ item.description }}
    </md-card-content>

    <hr />

    <md-card-action>
      <ul class="technologies">
        <li v-for="(technology, index) in item.techStack" :key="index">{{ technology }} &bull; &nbsp;</li>
      </ul>
    </md-card-action>
  </md-card>
</template>

<script>
import githubImg from './../assets/technologies/GitHub-Gray-32px.png';

export default {
  name: 'Layouts',
  props: {
    item: Object,
    default: () => ({
      title: 'Title',
      subTitle: '',
      description: '',
      img: '',
      alt: '',
      githubUrl: '',
      techStack: [],
      isNew: false,
    }),
  },
  data: () => ({
    githubImg,
  }),
};
</script>

<style lang="scss" scoped>
.md-card {
  min-height: 440px;
  width: 320px;
  margin: 4px;
  display: inline-block;
  vertical-align: top;

  .new-banner {
    background-color: #31afc2;
    color: white;
    font-size: 12px;
    font-weight: 500;
    padding: 1px 12px;
    transform: rotate(-35deg);
    display: inline-block;
    position: absolute;
    top: 12px;
    left: -7px;
    border-radius: 25px 0px 25px 0px;
  }

  .md-title {
    position: relative;
    font-weight: 500;

    .github-icon {
      float: right;
      position: absolute;
      right: 0px;
    }
  }

  .md-subhead {
    overflow: hidden;
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-line-clamp: 1;
  }

  hr {
    width: 70%;
    border: none;
    height: 1px;
    background-color: rgba(0, 0, 0, 0.12);
  }

  .technologies {
    padding-left: 0;
    margin: 0px 16px 10px 16px;
    overflow: hidden;
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-line-clamp: 2;
    // color: #e60c70;
    color: #a693d8;
    li {
      display: inline;
    }
  }
}

.md-card-content {
  overflow: hidden;
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-line-clamp: 3;
}

.md-card-media img {
  width: 80%;
}
</style>
