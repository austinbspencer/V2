<template>
  <b-container>
  <b-row align-v="center">
    <b-col md="3" v-for="(obj, key) in portfolioJSON" :key="key">
      <b-card :img-src="`${loadImg(obj.img)}`"
      img-alt="Job-info" img-top tag="article" style="max-width:20rem" class="mb-2">
        <b-card-text>
          {{ obj.desc }}
        </b-card-text>
        <side-toggle v-once></side-toggle>
         <!-- :href="`${loadLink(obj.link)}`" -->
      </b-card>
    </b-col>
  </b-row>
</b-container>
</template>

<script>
// @ is an alias to /src
import SideToggle from '@/components/SideToggle.vue'
import ProjectCard from '@/components/ProjectCard.vue'

export default {
  name: "Home",
  components: {
    'side-toggle': SideToggle,
    'project-card': ProjectCard
  },
  data: () => ({
        portfolioJSON: [
            {
                img: "Python_(programming_language)/Python_(programming_language)-Logo.wine.svg",
                link: "Python/",
                caption: 'Python',
                desc: 'My projects that are written in Python'
            },
            {
                img: 'Go_(programming_language)/Go_(programming_language)-Logo.wine.svg',
                link: "Go/",
                caption: 'Go',
                desc: 'My projects that are written in Go'
            },
            {
                img: 'Vue.js/Vue.js-Logo.wine.svg',
                link: "JavaScript/",
                caption: 'Vue.js',
                desc: 'My projects that implement Vue framework'
            },
            {
                img: 'Redis/Redis-Logo.wine.svg',
                link: "redis/",
                caption: 'Redis',
                desc: 'My projects that use Redis database'
            },
            {
                img: 'Docker_(software)/Docker_(software)-Logo.wine.svg',
                link: "Docker/",
                caption: 'Docker',
                desc: 'My projects that are run as Docker containers'
            },
            {
                img: 'C%2B%2B/C%2B%2B-Logo.wine.svg',
                link: "Python/",
                caption: 'C++',
                desc: 'My projects that are written in C++'
            },
        ]
    }),
    methods: {
    loadImg(imgPath) {
      return ("https://www.logo.wine/a/logo/" + imgPath)
    },
    loadLink(linkPath) {
        return("https://austinspencer.works/projects/" + linkPath)
    },
    
  }
};
</script>

<style lang="scss" scoped>
  p.card-text {
    border-top: .5px solid black;
    padding-top: 10px;
    // border-bottom: .5px solid black;
  }
</style>