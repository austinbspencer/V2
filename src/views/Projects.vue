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
          <b-card-text> </b-card-text>
          <div>
            <b-button
              v-b-modal="obj.caption"
              @click="show = true"
              variant="secondary"
              >Show Projects</b-button
            >

            <b-modal
              :id="obj.caption"
              centered
              :title="obj.caption"
              :size="size"
              header-bg-variant="info"
              :body-bg-variant="variant"
              body-text-variant="primary"
              footer-bg-variant="dark"
              backdrop
              shadow
            >
              <div class="px-3 py-2">
                <b-form-group
                  label="Window Size (Browser Only)"
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
              <!-- First project template -->
              <template v-if="'desc' in obj">
                <div class="px-3 py-2">
                  <p>
                    {{ obj.desc }}
                  </p>
                  <b-img
                    v-if="'repo1' in obj"
                    :src="`${loadRepoStats(obj.repo1)}`"
                    fluid
                    thumbnail
                  ></b-img>
                  <br />
                  <br />
                  <div class="w-75">
                    <template v-if="'livelink1' in obj">
                      <b-dropdown
                        id="dropdown-1"
                        text="Project Links"
                        size="md"
                        variant="outline-secondary"
                        class="m-md-2"
                      >
                        <b-dropdown-item :href="`${loadRepo(obj.repo1)}`"
                          >GitHub</b-dropdown-item
                        >
                        <b-dropdown-item :href="obj.livelink1"
                          >Live</b-dropdown-item
                        >
                      </b-dropdown>
                    </template>
                    <template v-else>
                      <b-button
                        variant="outline-secondary"
                        :href="`${loadRepo(obj.repo1)}`"
                        >GitHub</b-button
                      >
                    </template>
                  </div>
                </div>
              </template>
              <!-- Second project template -->
              <template v-if="'desc2' in obj">
                <div class="px-3 py-2">
                  <p>
                    {{ obj.desc2 }}
                  </p>
                  <b-img
                    v-if="'repo2' in obj"
                    :src="`${loadRepoStats(obj.repo2)}`"
                    fluid
                    thumbnail
                  ></b-img>
                  <br />
                  <br />
                  <div class="w-75">
                    <template v-if="'livelink2' in obj">
                      <b-dropdown
                        id="dropdown-1"
                        text="Project Links"
                        size="md"
                        variant="outline-secondary"
                        class="m-md-2"
                      >
                        <b-dropdown-item :href="`${loadRepo(obj.repo2)}`"
                          >GitHub</b-dropdown-item
                        >
                        <b-dropdown-item :href="obj.livelink2"
                          >Live</b-dropdown-item
                        >
                      </b-dropdown>
                    </template>
                    <template v-else>
                      <b-button
                        variant="outline-secondary"
                        :href="`${loadRepo(obj.repo2)}`"
                        >GitHub</b-button
                      >
                    </template>
                  </div>
                </div>
              </template>
              <!-- 3rd project area -->
              <template v-if="'desc3' in obj">
                <div class="px-3 py-2">
                  <p>
                    {{ obj.desc3 }}
                  </p>
                  <b-img
                    v-if="'repo3' in obj"
                    :src="`${loadRepoStats(obj.repo3)}`"
                    fluid
                    thumbnail
                  ></b-img>
                  <br />
                  <br />
                  <div class="w-75">
                    <template v-if="'livelink3' in obj">
                      <b-dropdown
                        id="dropdown-1"
                        text="Project Links"
                        size="md"
                        variant="outline-secondary"
                        class="m-md-2"
                      >
                        <b-dropdown-item :href="`${loadRepo(obj.repo3)}`"
                          >GitHub</b-dropdown-item
                        >
                        <b-dropdown-item :href="obj.livelink3"
                          >Live</b-dropdown-item
                        >
                      </b-dropdown>
                    </template>
                    <template v-else-if="`repo3` in obj">
                      <b-button
                        variant="outline-secondary"
                        :href="`${loadRepo(obj.repo3)}`"
                        >GitHub</b-button
                      >
                    </template>
                  </div>
                </div>
              </template>
              <!-- Footer template -->
              <template v-slot:modal-footer="{ close }">
                <!-- Button with custom close trigger value -->
                <div class="w-100">
                  <b-button
                    size="sm"
                    variant="outline-secondary"
                    class="float-left"
                    href="https://github.com/abspen1"
                  >
                    GitHub
                  </b-button>
                  <!-- Emulate built in modal footer ok and cancel button actions -->
                  <b-button
                    size="sm"
                    variant="danger"
                    class="float-right"
                    @click="close()"
                  >
                    Close
                  </b-button>
                </div>
              </template>
            </b-modal>
          </div>
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
        repo1: "twitter-bot",
        livelink1: "https://austinspencer.works/twitter-bot/",

        desc2: "Algorithmic Trading",
        repo2: "alpaca-python",

        desc3: "Pacman Game",
        repo3: "PacMan-PyGame"
      },
      {
        img:
          "Go_(programming_language)/Go_(programming_language)-Logo.wine.svg",
        link: "Go/",
        caption: "Go",
        desc: "My website back-end built with Go",
        repo1: "go-backend",

        desc2: "Algorithmic Trading",
        repo2: "go-trading-algo"
      },
      {
        img: "Vue.js/Vue.js-Logo.wine.svg",
        link: "JavaScript/",
        caption: "Vue.js",
        desc: "This website!",
        repo1: "BootstrapVue-website",

        desc2: "Hangman Game",
        repo2: "hangman-js",
        livelink2: "https://austinspencer.works/hangman-js/",

        desc3: "Website V1",
        repo3: "abspen1.github.io",
        livelink3: "https://austinspencer.works/"
      },
      {
        img: "Redis/Redis-Logo.wine.svg",
        link: "redis/",
        caption: "Redis",
        desc: "Twitter Bot",
        repo1: "twitter-bot",

        desc2: "My website back-end built with Go",
        repo2: "go-backend",

        desc3:
          "Most of my projects are built with Redis database. Check out more of my open-sourced projects on my GitHub!"
      },
      {
        img: "Docker_(software)/Docker_(software)-Logo.wine.svg",
        link: "Docker/",
        caption: "Docker",
        desc: "Twitter Bot",
        repo1: "twitter-bot",

        desc2: "My website back-end built with Go",
        repo2: "go-backend",

        desc3: "Demo of using Docker with several lanuages",
        repo3: "docker-demo"
      },
      {
        img: "C%2B%2B/C%2B%2B-Logo.wine.svg",
        link: "Python/",
        caption: "C++",
        desc:
          "I don't currently have any open-source projects built with C++. Follow my GitHub to see when I do!"
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
    sizes: ["sm", "md", "lg", "xl"]
  }),
  methods: {
    loadImg(imgPath) {
      return "https://www.logo.wine/a/logo/" + imgPath;
    },
    loadLink(linkPath) {
      return "https://austinspencer.works/projects/" + linkPath;
    },
    loadRepo(repoPath) {
      return "https://github.com/abspen1/" + repoPath;
    },
    loadRepoStats(repoPath) {
      return (
        "https://github-readme-stats.vercel.app/api/pin/?username=abspen1&repo=" +
        repoPath +
        "&theme=default_repocard"
      );
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
.custom-select {
  width: 33%;
}
</style>
