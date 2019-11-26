<template>
  <md-card>
    <md-card-header>
      <span v-if="item.status === 'new'" class="banner-new">
        New
      </span>
      <span v-if="item.status === 'inProgress'" class="banner-progress">
        In Progress
      </span>
      <div class="md-title">
        {{ item.title }}
        <span class="github-icon">
          <a title="Github Repo" :href="item.githubUrl" target="blank">
            <img :src="githubImg" alt="Github Repository" />
          </a>
        </span>
      </div>
      <div class="md-subhead">{{ item.subTitle }}</div>
    </md-card-header>

    <md-card-media>
      <iframe v-if="item.isVideo" title="video player" :src="item.img" />
      <img v-else :src="item.img" :alt="item.alt" />
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
import githubImg from './../assets/socialMedia/github-gray-32.png';

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
.banner {
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

.line-clamp {
  overflow: hidden;
  display: -webkit-box;
  -webkit-box-orient: vertical;
}

.md-card {
  min-height: 440px;
  width: 320px;
  margin: 4px;
  display: inline-block;
  vertical-align: top;

  .banner-new {
    @extend .banner;
    background-color: #31afc2;
    top: 12px;
    left: -7px;
  }

  .banner-progress {
    @extend .banner;
    background-color: rgb(220, 19, 59);
    top: 22px;
    left: -11px;
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
    @extend .line-clamp;
    -webkit-line-clamp: 1;
  }

  hr {
    width: 70%;
    border: none;
    height: 1px;
    background-color: rgba(0, 0, 0, 0.12);
  }

  .technologies {
    @extend .line-clamp;
    -webkit-line-clamp: 2;
    padding-left: 0;
    margin: 0px 16px 10px 16px;
    color: #a693d8;
    li {
      display: inline;
    }
  }
}

.md-card-content {
  @extend .line-clamp;
  -webkit-line-clamp: 3;
}

.md-card-media img {
  width: 80%;
}
</style>
