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
            {{ obj.desc }}
          </b-card-text>
          <div id="SideToggle">
            <b-button v-b-toggle="obj.caption">View Projects</b-button>

            <b-sidebar
              :id="obj.caption"
              :title="obj.caption"
              :backdrop-variant="variant"
              backdrop
              shadow
            >
              <div class="px-3 py-2">
                <b-form-group
                  label="Backdrop variant"
                  label-for="backdrop-variant"
                >
                  <b-form-select
                    id="backdrop-variant"
                    v-model="variant"
                    :options="variants"
                  ></b-form-select>
                </b-form-group>
              </div>
              <div class="px-3 py-2">
                <p>
                  {{ obj.desc }}
                </p>
                <b-img :src="obj.repo1" fluid thumbnail></b-img>
              </div>
              <div class="px-3 py-2">
                <p>
                  {{ obj.desc2 }}
                </p>
                <b-img :src="obj.repo2" fluid thumbnail></b-img>
              </div>
            </b-sidebar>
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
        desc: "My projects that are built with Python",
        repo1:
          "https://github-readme-stats.vercel.app/api/pin/?username=abspen1&repo=twitter-bot&theme=graywhite",
        repo2:
          "https://github-readme-stats.vercel.app/api/pin/?username=abspen1&repo=alpaca-python&theme=graywhite"
      },
      {
        img:
          "Go_(programming_language)/Go_(programming_language)-Logo.wine.svg",
        link: "Go/",
        caption: "Go",
        desc: "My projects that are built with Go",
        repo1:
          "https://github-readme-stats.vercel.app/api/pin/?username=abspen1&repo=twitter-bot&theme=graywhite",
        repo2:
          "https://github-readme-stats.vercel.app/api/pin/?username=abspen1&repo=alpaca-python&theme=graywhite"
      },
      {
        img: "Vue.js/Vue.js-Logo.wine.svg",
        link: "JavaScript/",
        caption: "Vue.js",
        desc: "My projects that implement Vue framework",
        repo1:
          "https://github-readme-stats.vercel.app/api/pin/?username=abspen1&repo=twitter-bot&theme=graywhite",
        repo2:
          "https://github-readme-stats.vercel.app/api/pin/?username=abspen1&repo=alpaca-python&theme=graywhite"
      },
      {
        img: "Redis/Redis-Logo.wine.svg",
        link: "redis/",
        caption: "Redis",
        desc: "My projects that use Redis database",
        repo1:
          "https://github-readme-stats.vercel.app/api/pin/?username=abspen1&repo=twitter-bot&theme=graywhite",
        repo2:
          "https://github-readme-stats.vercel.app/api/pin/?username=abspen1&repo=alpaca-python&theme=graywhite"
      },
      {
        img: "Docker_(software)/Docker_(software)-Logo.wine.svg",
        link: "Docker/",
        caption: "Docker",
        desc: "My projects that are run as Docker containers",
        repo1:
          "https://github-readme-stats.vercel.app/api/pin/?username=abspen1&repo=twitter-bot&theme=graywhite"
      },
      {
        img: "C%2B%2B/C%2B%2B-Logo.wine.svg",
        link: "Python/",
        caption: "C++",
        desc: "My projects that are built with C++",
        repo1:
          "https://github-readme-stats.vercel.app/api/pin/?username=abspen1&repo=twitter-bot&theme=graywhite",
        repo2:
          "https://github-readme-stats.vercel.app/api/pin/?username=abspen1&repo=alpaca-python&theme=graywhite"
      }
    ],
    variant: "dark",
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
    ]
  }),
  methods: {
    loadImg(imgPath) {
      return "https://www.logo.wine/a/logo/" + imgPath;
    },
    loadLink(linkPath) {
      return "https://austinspencer.works/projects/" + linkPath;
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
