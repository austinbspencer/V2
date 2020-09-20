<template>
  <div>
      <b-col>
      <b-card 
        :img-src="`${loadImg(img)}`"
        img-alt="Proj-info" 
        img-top tag="article" 
        style="max-width:20rem" 
        class="mb-2"
        >
        <b-card-text>
          :"name"
        </b-card-text>
        <a :href="`${loadLink(link)}`">
          <b-button variant="primary">Click Me</b-button>
        </a>
      </b-card>
    </b-col>
  </div>
</template>

<script>
export default {
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
    
<style>

</style>