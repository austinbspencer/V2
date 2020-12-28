<template>
  <b-container class="projects">
    <link
      rel="stylesheet"
      href="https://use.fontawesome.com/releases/v5.2.0/css/all.css"
      integrity="sha384-hWVjflwFxL6sNzntih27bfxkr27PmbbK/iSvJ+a4+0owXq79v+lsFkW54bOGbiDQ"
      crossorigin="anonymous"
    />
    <br />
    <b-button
      id="dark-outline"
      size="lg"
      variant="outline-dark"
      class="float-center"
      href="https://austinspencer.works/next-project/"
    >
      Project Ideas
    </b-button>
    <b-row align-v="center">
      <b-col md="4" v-for="(obj, key) in portfolioJSON" :key="key">
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
              header-bg-variant="primary"
              header-text-variant="light"
              body-bg-variant="light"
              body-text-variant="dark"
              footer-bg-variant="dark"
              backdrop
            >
              <!-- <div class="px-3 py-2">
                <h1>Interactive Styles!!</h1> -->
              <!-- Window Size -->
              <!-- <b-form-group
                  label="Window Size (Browser Only)"
                  v-model="size"
                  :options="sizes"
                >
                  <b-form-select
                    id="backdrop-variant"
                    v-model="size"
                    :options="sizes"
                  ></b-form-select>
                </b-form-group> -->
              <!-- Background Color -->
              <!-- <b-form-group
                  label="Background Color"
                  v-model="variant"
                  :options="variants"
                >
                  <b-form-select
                    id="backdrop-variant"
                    v-model="variant"
                    :options="variants"
                  ></b-form-select>
                </b-form-group> -->
              <!-- Text Color -->
              <!-- <b-form-group
                  label="Text Color"
                  v-model="primary"
                  :options="variants"
                >
                  <b-form-select
                    id="backdrop-variant"
                    v-model="primary"
                    :options="variants"
                  ></b-form-select>
                </b-form-group> -->
              <!-- </div> -->
              <!-- First project template -->
              <template v-if="'desc' in obj">
                <div class="px-3 py-2">
                  <p>
                    {{ obj.desc }}
                  </p>
                  <b-img
                    v-if="'repo1' in obj"
                    :src="`${loadRepoStats(obj.repo1, obj.user1)}`"
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
                        variant="outline-dark"
                        class="m-md-2"
                      >
                        <b-dropdown-item
                          :href="`${loadRepo(obj.repo1, obj.user1)}`"
                          ><i class="fab fa-github"></i> GitHub</b-dropdown-item
                        >
                        <b-dropdown-item :href="obj.livelink1"
                          ><i class="fas fa-laptop-code"></i>
                          Live</b-dropdown-item
                        >
                      </b-dropdown>
                    </template>
                    <template v-else>
                      <b-button
                        variant="outline-dark"
                        :href="`${loadRepo(obj.repo1, obj.user1)}`"
                        ><i class="fab fa-github"></i> GitHub</b-button
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
                    :src="`${loadRepoStats(obj.repo2, obj.user2)}`"
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
                        variant="outline-dark"
                        class="m-md-2"
                      >
                        <b-dropdown-item
                          :href="`${loadRepo(obj.repo2, obj.user2)}`"
                          ><i class="fab fa-github"></i> GitHub</b-dropdown-item
                        >
                        <b-dropdown-item :href="obj.livelink2"
                          ><i class="fas fa-laptop-code"></i>
                          Live</b-dropdown-item
                        >
                      </b-dropdown>
                    </template>
                    <template v-else>
                      <b-button
                        variant="outline-dark"
                        :href="`${loadRepo(obj.repo2, obj.user2)}`"
                        ><i class="fab fa-github"></i> GitHub</b-button
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
                    :src="`${loadRepoStats(obj.repo3, obj.user3)}`"
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
                        variant="outline-dark"
                        class="m-md-2"
                      >
                        <b-dropdown-item
                          :href="`${loadRepo(obj.repo3, obj.user3)}`"
                          ><i class="fab fa-github"></i> GitHub</b-dropdown-item
                        >
                        <b-dropdown-item :href="obj.livelink3"
                          ><i class="fas fa-laptop-code"></i>
                          Live</b-dropdown-item
                        >
                      </b-dropdown>
                    </template>
                    <template v-else-if="`repo3` in obj">
                      <b-button
                        variant="outline-dark"
                        :href="`${loadRepo(obj.repo3, obj.user3)}`"
                        ><i class="fab fa-github"></i> GitHub</b-button
                      >
                    </template>
                  </div>
                </div>
              </template>
              <!-- 4th project area -->
              <template v-if="'desc4' in obj">
                <div class="px-3 py-2">
                  <p>
                    {{ obj.desc4 }}
                  </p>
                  <b-img
                    v-if="'repo4' in obj"
                    :src="`${loadRepoStats(obj.repo4, obj.user4)}`"
                    fluid
                    thumbnail
                  ></b-img>
                  <br />
                  <br />
                  <div class="w-75">
                    <template v-if="'livelink4' in obj">
                      <b-dropdown
                        id="dropdown-1"
                        text="Project Links"
                        size="md"
                        variant="outline-dark"
                        class="m-md-2"
                      >
                        <b-dropdown-item
                          :href="`${loadRepo(obj.repo4, obj.user4)}`"
                          ><i class="fab fa-github"></i> GitHub</b-dropdown-item
                        >
                        <b-dropdown-item :href="obj.livelink4"
                          ><i class="fas fa-laptop-code"></i>
                          Live</b-dropdown-item
                        >
                      </b-dropdown>
                    </template>
                    <template v-else-if="`repo4` in obj">
                      <b-button
                        variant="outline-dark"
                        :href="`${loadRepo(obj.repo4, obj.user)}`"
                        ><i class="fab fa-github"></i> GitHub</b-button
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
                    id="success-outline"
                    size="sm"
                    variant="dark"
                    class="float-left"
                    href="https://github.com/abspen1"
                    ><i class="fab fa-github"></i> GitHub</b-button
                  >
                  <!-- Emulate built in modal footer ok and cancel button actions -->
                  <b-button
                    id="danger"
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
    <br />
  </b-container>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'Home',
  components: {},
  data: () => ({
    portfolioJSON: [
      {
        img:
          'Python_(programming_language)/Python_(programming_language)-Logo.wine.svg',
        // link: "Python/",
        caption: 'Python',
        desc: 'Twitter Bot',
        user1: 'abspen1',
        repo1: 'twitter-bot',
        livelink1: '/twitter-bot/',

        user2: 'abspen1',
        desc2: 'Algorithmic Trading',
        repo2: 'alpaca-python',

        user3: 'abspen1',
        desc3: 'Pacman Game',
        repo3: 'PacMan-PyGame',

        user4: 'battle-of-the-states',
        desc4: 'Fantasy football league webpage and automated twitter account',
        repo4: '',
        livelink4: '/BOTS-FFL/',
      },
      {
        img:
          'Go_(programming_language)/Go_(programming_language)-Logo.wine.svg',
        caption: 'Go',
        desc: 'My website back-end built with Go',
        user1: 'abspen1',
        repo1: 'go-backend',

        desc2: 'Algorithmic Trading',
        user2: 'abspen1',
        repo2: 'go-trading-algo',

        desc3: 'Automated birthday emailer',
        user3: 'abspen1',
        repo3: 'bday-email',

        desc4: 'Compressing messages with custom encoder',
        user4: 'abspen1',
        repo4: 'go-encode',
      },
      {
        img: 'Vue.js/Vue.js-Logo.wine.svg',
        caption: 'Vue.js',
        desc: 'This website!',
        user1: 'abspen1',
        repo1: 'V2',
      },
      {
        img: 'Node.js/Node.js-Logo.wine.svg',
        caption: 'JavaScript Projects',

        desc:
          'Rock Paper Scissors Game with back-end save data function, Repo is private but the live link is still working!',
        user1: 'abspen1',
        repo1: 'discord-bot',
        // livelink1: "/rps-js/",

        desc2: 'Hangman Game, my first JavaScript project',
        user2: 'abspen1',
        repo2: 'hangman-js',
        livelink2: '/hangman-js/',

        desc3: 'Website V1',
        user3: 'abspen1',
        repo3: 'abspen1.github.io',
        livelink3: '/',
      },
      // {
      //   img: 'Redis/Redis-Logo.wine.svg',
      //   caption: 'Redis',
      //   desc: 'Twitter Bot',
      //   repo1: 'twitter-bot',
      //   livelink1: '/twitter-bot/',

      //   desc2: 'My website back-end built with Go',
      //   repo2: 'go-backend',

      //   desc3:
      //     'Most of my projects are built with Redis database. Check out more of my open-sourced projects on my GitHub!',
      // },
      // {
      //   img: 'Docker_(software)/Docker_(software)-Logo.wine.svg',
      //   caption: 'Docker',
      //   desc: 'Twitter Bot',
      //   repo1: 'twitter-bot',
      //   livelink1: '/twitter-bot/',

      //   desc2: 'My website back-end built with Go',
      //   repo2: 'go-backend',

      //   desc3: 'Demo of using Docker with several lanuages',
      //   repo3: 'docker-demo',
      // },
      {
        img: 'Google_Cloud_Platform/Google_Cloud_Platform-Logo.wine.svg',
        caption: 'Current Project',

        desc:
          'Twitter Bot, implements Redis & Docker on Google Cloud VM Instance',
        user1: 'abspen1',
        repo1: 'twitter-bot',
        livelink1: '/twitter-bot/',

        desc2: 'Battle of the States Fantasy Football League',
        user2: 'abspen1',
        repo2: 'battle-of-the-states',
        livelink2: '/BOTS-FFL/',
      },
      {
        img:
          'Java_(programming_language)/Java_(programming_language)-Logo.wine.svg',
        caption: 'Java',
        desc: 'Interactive coffee shop',
        user1: 'abspen1',
        repo1: 'coffee-shop',
        livelink1: '/projects/java/demos/coffee/',

        desc2: 'Teacher attendance tracker GUI',
        user2: 'abspen1',
        repo2: 'asu-cse-source-code/360-Final-Project',
        livelink2: '/projects/java/demos/gui/',
      },
      {
        img: 'C%2B%2B/C%2B%2B-Logo.wine.svg',
        caption: 'C++',
        desc: 'Encoder/Decoder for txt file compression',
        user1: 'abspen1',
        repo1: 'cse-310-encode-decode',

        desc2: 'Interactive App Store',
        user2: 'battle-of-the-states',
        repo2: 'asu-cse-source-code/cse-310-app-store',
      },
    ],
    variant: 'white',
    primary: 'primary',
    variants: [
      'white',
      'light',
      'dark',
      'primary',
      'secondary',
      'success',
      'danger',
      'warning',
      'info',
    ],
    size: 'lg',
    sizes: ['sm', 'md', 'lg', 'xl'],
  }),
  methods: {
    loadImg(imgPath) {
      return 'https://www.logo.wine/a/logo/' + imgPath
    },
    loadLink(linkPath) {
      return 'https://austinspencer.works/projects/' + linkPath
    },
    loadRepo(repoPath, user) {
      return `https://github.com/${user}/` + repoPath
    },
    loadRepoStats(repoPath, user) {
      return (
        `https://github-readme-stats.vercel.app/api/pin/?username=${user}&repo=` +
        repoPath +
        '&theme=default_repocard'
      )
    },
  },
}
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
.projects {
  padding-bottom: 4rem;
}
</style>
