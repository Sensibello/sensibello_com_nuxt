<template>
  <section class="home">
   <two-col-text :items="[
      {
          header: 'Welcome', 
          description: `Karli is a passionate frontend developer from Cleveland, Ohio. She strives to build beautiful, accessible, responsive, and clean website with intuitive user experiences. \n \n She has developed websites for a large range of clients from all different types of sectors. Prior to her current position as a Senior Frontend Developer at Progressive's in-house marketing agency, ninety6, she worked on several teams as a frontend developer, web designer, and UX developer. \n \n Her approach to building websites centers around being accessible and memorable, with the goal being to always leaving a good impression to everyone who accesses it.`,
          url: '/contact',
          linkText: 'Get in touch',
      }
    ]" />
    
   <two-image-with-text :items="[
      {
          subhead:'What I do',
          header: 'Welcome', 
          description: 'I am a front end developer from Cleveland, Ohio. I strive to build beautiful, responsive, and clean website with intuitive user experiences.', 
          url: '/',
          linkText: 'link url',
          imageLeft:'east-fourth.jpg',
          imageRight:'cleveland-sign.jpg',
      }
    ]" />
</section>

</template>

<script lang="ts">
import twoColText from '~/components/partials/twoColText.vue';
import twoImageWithText from '@/components/partials/twoImageWithText.vue';
import { Component, Vue } from 'nuxt-property-decorator';
import settings from '@/content/settings/general.json';

@Component({
  components: {
    twoColText,
    twoImageWithText,
  },

   transition() {
    return 'slide-left';
  },

})

export default class Home extends Vue {
  welcomeText = settings.welcomeText;
}
</script>
