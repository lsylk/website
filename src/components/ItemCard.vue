<template>
  <md-card :md-with-hover="item.status !== 'inProgress'" :class="{ 'disable-item-card': isDisabled }">
    <div class="card" @click="openGithubRepo">
      <md-card-header>
        <span v-if="item.status === 'new'" class="banner-new">
          New
        </span>
        <span v-if="item.status === 'inProgress'" class="banner-progress">
          In Progress
        </span>
        <span v-if="item.status === 'inProgressRelease'" class="banner-improvement">
          In Progress
        </span>
        <div class="md-title">
          {{ item.title }}
          <span v-if="item.status !== 'work'" class="github-icon">
            <a title="Github Repo" :href="item.githubUrl" target="blank" @click="openGithubRepo">
              <img :src="githubImg" alt="Github Repository" />
            </a>
          </span>
        </div>
        <div class="md-subhead">{{ item.subTitle }}</div>
      </md-card-header>

      <md-card-media :class="item.isVideo ? 'itemCardVideo' : ''">
        <span v-if="item.status === 'inProgress'" class="banner-coming-soon">
          Coming Soon...
        </span>
        <iframe v-if="item.isVideo && item.status === 'inProgress'" title="video player" :src="item.img" />
        <video
          v-else-if="item.isVideo && item.status === 'inProgressRelease'"
          controls=""
          name="media"
          title="video player"
        >
          <source :src="item.img" type="video/mp4" />
        </video>
        <img v-else-if="!item.isVideo" :src="item.img" :alt="item.alt" />
      </md-card-media>

      <hr />

      <md-card-content>
        {{ item.description }}
      </md-card-content>

      <hr />

      <md-card-content>
        <ul class="technologies">
          <li v-for="(technology, index) in item.techStack" :key="index">{{ technology }} &bull; &nbsp;</li>
        </ul>
      </md-card-content>
    </div>
  </md-card>
</template>

<script>
import githubImg from './../assets/socialMedia/github-gray-32.png';

export default {
  name: 'Layouts',
  props: {
    item: {
      type: Object,
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
  },
  data: () => ({
    githubImg,
  }),
  computed: {
    isDisabled() {
      return this.item.status === 'inProgress';
    },
  },
  methods: {
    openGithubRepo() {
      if (this.item.status !== 'inProgress') {
        window.open(this.item.githubUrl, '_blank');
      }
    },
  },
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

.disable-item-card {
  background-color: #dcdcdcc7 !important;
}

.md-card {
  min-height: 474px;
  max-height: 474px;
  width: 320px;
  margin-top: 16px;
  margin-bottom: 16px;
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
    // background-color: rgb(220, 19, 59);
    background-color: rgba(220, 19, 59, 0.49);
    top: 22px;
    left: -11px;
  }

  .banner-improvement {
    @extend .banner;
    background-color: rgb(220, 19, 59);
    top: 22px;
    left: -11px;
  }

  .banner-coming-soon {
    @extend .banner;
    top: 68px;
    left: 59px;
    color: rgba(220, 19, 59, 0.49);
    font-size: 26px;
    transform: none;
    text-shadow: 2px 2px 2px #d0cccd;
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
  .itemCardVideo {
    video {
      border: 1px solid #80808036;
      max-height: 185px;
    }
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
  width: auto;
}

@media all and (max-width: 375px) {
  .md-card {
    max-width: 300px;
    padding: 10px;
  }
}
</style>
