<template>
  <b-container>
  <b-row align-v="center">
    <b-col md="3" v-for="(obj, key) in portfolioJSON" :key="key">
      <b-card title="This Is a Card" :img-src="`${loadImg(obj.img)}`"
      img-alt="Job-info" img-top tag="article" style="max-width:20rem" class="mb-2" footer="Card Footer">
        <b-card-text>
          Lorem, ipsum dolor sit amet consectetur adipisicing elit. Hic, aliquam?
        </b-card-text>
        <b-button variant="primary">Apply</b-button>
      </b-card>
    </b-col>
  </b-row>
</b-container>
</template>

<script>
// @ is an alias to /src

export default {
  name: "Home",
  components: {
  },
  data: () => ({
        portfolioJSON: [
            {
                img: "Python_(programming_language)/Python_(programming_language)-Logo.wine.svg",
                link: "Python/",
                caption: 'Python'
            },
            {
                img: 'Go_(programming_language)/Go_(programming_language)-Logo.wine.svg',
                link: "Go/",
                caption: 'Go'
            },
            {
                img: 'Vue.js/Vue.js-Logo.wine.svg',
                link: "JavaScript/",
                caption: 'Vue.js'
            },
            {
                img: 'Redis/Redis-Logo.wine.svg',
                link: "redis/",
                caption: 'Redis'
            },
            {
                img: 'Docker_(software)/Docker_(software)-Logo.wine.svg',
                link: "Docker/",
                caption: 'Docker'
            },
            {
                img: 'C%2B%2B/C%2B%2B-Logo.wine.svg',
                link: "Python/",
                caption: 'C++'
            },
        ]
    }),
    methods: {
    loadImg(imgPath) {
      return ("https://www.logo.wine/a/logo/" + imgPath)
    },
    loadLink(linkPath) {
        return("https://austinspencer.works/projects/" + linkPath)
    }
  }
};
</script>
