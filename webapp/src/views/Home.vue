<template>
  <b-container>
    <b-row align-v="center">
      <b-col md="3" v-for="(obj, key) in portfolioJSON" :key="key">
        <b-card
          :img-src="`${loadImg(obj.img)}`"
          img-alt="Job-info"
          img-top
          tag="article"
          style="max-width:20rem"
          class="mb-2"
        >
          <b-card-text>
            
          </b-card-text>
          <div id="SideToggle">
            <b-button v-b-modal="obj.caption" @click="show=true" variant="secondary">Show Projects</b-button>

            <b-modal
              :id="obj.caption"
              centered
              :title="obj.caption"
              :size="size"
              header-bg-variant="info"
              :body-bg-variant="variant"
              footer-bg-variant="dark"
              backdrop
              shadow
            >
              <div class="px-3 py-2">
                <b-form-group
                label="Window Size"
                  v-model="size"
                  :options="sizes"
                >
                  <b-form-select
                    id="backdrop-variant"
                    v-model="size"
                    :options="sizes"
                  ></b-form-select>
                </b-form-group>
              </div>
              <div class="px-3 py-2">
                <p>
                  {{ obj.desc }}
                </p>
                <b-img :src="obj.repo1" fluid thumbnail></b-img>
                <template v-if="'repo1' in obj">
                  &nbsp;
                  &nbsp;
                  <b-button  variant="outline-secondary" :href="obj.repolink1">GitHub</b-button>
                  &nbsp;
                  &nbsp;
                  <b-button v-if="'livelink1' in obj"  variant="outline-primary" :href="obj.livelink1">Live</b-button>
                </template>
              </div>
              <div class="px-3 py-2">
                <p>
                  {{ obj.desc2 }}
                </p>
                <b-img :src="obj.repo2" fluid thumbnail></b-img>
                <template v-if="'repo2' in obj">
                  &nbsp;
                  &nbsp;
                  <b-button  variant="outline-secondary" :href="obj.repolink2">GitHub</b-button>
                  &nbsp;
                  &nbsp;
                  <b-button v-if="'livelink2' in obj"  variant="outline-primary" :href="obj.livelink2">Live</b-button>
                </template>
              </div>
              <div class="px-3 py-2">
                <p>
                  {{ obj.desc2 }}
                </p>
                <b-img :src="obj.repo3" fluid thumbnail></b-img>
                <template v-if="'repo3' in obj">
                  &nbsp;
                  &nbsp;
                  <b-button  variant="outline-secondary" :href="obj.repolink3">GitHub</b-button>
                  &nbsp;
                  &nbsp;
                  <b-button v-if="'livelink3' in obj"  variant="outline-primary" :href="obj.livelink3">Live</b-button>
                </template>
              </div>
            </b-modal>
          </div>
          <!-- :href="`${loadLink(obj.link)}`" -->
        </b-card>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
// @ is an alias to /src

export default {
  name: "Home",
  components: {},
  data: () => ({
    portfolioJSON: [
      {
        img:
          "Python_(programming_language)/Python_(programming_language)-Logo.wine.svg",
        link: "Python/",
        caption: "Python",
        desc: "Twitter Bot",
        repo1:
          "https://github-readme-stats.vercel.app/api/pin/?username=abspen1&repo=twitter-bot&theme=graywhite",
        repolink1: "https://github.com/abspen1/twitter-bot",
        livelink1: "https://austinspencer.works/twitter-bot/",

        desc2: "Algorithmic Trading",
        repo2:
          "https://github-readme-stats.vercel.app/api/pin/?username=abspen1&repo=alpaca-python&theme=graywhite",
        repolink2: "https://github.com/abspen1/alpaca-python",

        desc3: "Pacman Game",
        repo3:
        "https://github-readme-stats.vercel.app/api/pin/?username=abspen1&repo=PacMan-PyGame&theme=graywhite",
        repolink3: "https://github.com/abspen1/PacMan-PyGame",

      },
      {
        img:
          "Go_(programming_language)/Go_(programming_language)-Logo.wine.svg",
        link: "Go/",
        caption: "Go",
        desc: "My projects built with Go",
        desc2: "My projects built with Go",
        repo1:
          "https://github-readme-stats.vercel.app/api/pin/?username=abspen1&repo=twitter-bot&theme=graywhite",
        repo2:
          "https://github-readme-stats.vercel.app/api/pin/?username=abspen1&repo=alpaca-python&theme=graywhite"
      },
      {
        img: "Vue.js/Vue.js-Logo.wine.svg",
        link: "JavaScript/",
        caption: "Vue.js",
        desc: "My projects built with Vue.js",
        desc2: "My projects built with Vue.js",
        repo1:
          "https://github-readme-stats.vercel.app/api/pin/?username=abspen1&repo=twitter-bot&theme=graywhite",
        repo2:
          "https://github-readme-stats.vercel.app/api/pin/?username=abspen1&repo=alpaca-python&theme=graywhite",
        livelink1: "novalue"
      },
      {
        img: "Redis/Redis-Logo.wine.svg",
        link: "redis/",
        caption: "Redis",
        desc: "My projects implementing Redis",
        desc2: "My projects implementing Redis",
        repo1:
          "https://github-readme-stats.vercel.app/api/pin/?username=abspen1&repo=twitter-bot&theme=graywhite",
        repo2:
          "https://github-readme-stats.vercel.app/api/pin/?username=abspen1&repo=alpaca-python&theme=graywhite",
        livelink1: 'novalue'
      },
      {
        img: "Docker_(software)/Docker_(software)-Logo.wine.svg",
        link: "Docker/",
        caption: "Docker",
        desc: "My projects that run as Docker containers",
        desc2: "My projects that run as Docker containers",
        repo1:
          "https://github-readme-stats.vercel.app/api/pin/?username=abspen1&repo=twitter-bot&theme=graywhite"
      },
      {
        img: "C%2B%2B/C%2B%2B-Logo.wine.svg",
        link: "Python/",
        caption: "C++",
        desc: "My projects built with C++",
        desc2: "My projects built with C++",
        repo2:
          "https://github-readme-stats.vercel.app/api/pin/?username=abspen1&repo=alpaca-python&theme=graywhite"
      }
    ],
    variant: "white",
    variants: [
      "transparent",
      "white",
      "light",
      "dark",
      "primary",
      "secondary",
      "success",
      "danger",
      "warning",
      "info"
    ],
    size: "lg",
    sizes: [
      "sm",
      "md",
      "lg",
      "xl"
    ]
  }),
  methods: {
    loadImg(imgPath) {
      return "https://www.logo.wine/a/logo/" + imgPath;
    },
    loadLink(linkPath) {
      return "https://austinspencer.works/projects/" + linkPath;
    },
  
    containsKey(obj, key ) {
        return Object.keys(obj).includes(key);
    }, 
  },
  computed: {
        hasName() {
            return this.containsKey(this.obj, 'livelink1');
        }
    }
};
</script>

<style lang="scss" scoped>
p.card-text {
  border-top: 0.5px solid black;
  padding-top: 10px;
  // border-bottom: .5px solid black;
}
.col,
.col-1,
.col-10,
.col-11,
.col-12,
.col-2,
.col-3,
.col-4,
.col-5,
.col-6,
.col-7,
.col-8,
.col-9,
.col-auto,
.col-lg,
.col-lg-1,
.col-lg-10,
.col-lg-11,
.col-lg-12,
.col-lg-2,
.col-lg-3,
.col-lg-4,
.col-lg-5,
.col-lg-6,
.col-lg-7,
.col-lg-8,
.col-lg-9,
.col-lg-auto,
.col-md,
.col-md-1,
.col-md-10,
.col-md-11,
.col-md-12,
.col-md-2,
.col-md-3,
.col-md-4,
.col-md-5,
.col-md-6,
.col-md-7,
.col-md-8,
.col-md-9,
.col-md-auto,
.col-sm,
.col-sm-1,
.col-sm-10,
.col-sm-11,
.col-sm-12,
.col-sm-2,
.col-sm-3,
.col-sm-4,
.col-sm-5,
.col-sm-6,
.col-sm-7,
.col-sm-8,
.col-sm-9,
.col-sm-auto,
.col-xl,
.col-xl-1,
.col-xl-10,
.col-xl-11,
.col-xl-12,
.col-xl-2,
.col-xl-3,
.col-xl-4,
.col-xl-5,
.col-xl-6,
.col-xl-7,
.col-xl-8,
.col-xl-9,
.col-xl-auto {
  padding-top: 2rem;
}
.b-sidebar {
  width: 500px;
}
</style>
