<template>
    <div class="two-image-with-text white-background border-bottom">
      <div class="container mx-auto relative-position">
        <div class="py-24 md:py-36 mx-auto flex flex-wrap flex-col md:flex-row items-center">
          <div class="flex flex-col w-full justify-center overflow-y-hidden">
            <!-- <div v-html="$md.render(welcomeText)" class="home__welcome markdown" /> -->
            <div class="grid grid-cols-1 md:grid-cols-2" v-for="item in items" :key="item.name">
              <div class="row-span-3 col-span-1">
                  <div class="img-shadow">
                    <img :src="require(`~/assets/images/${item.imageLeft}`)" :alt="`${item.header} graphic`"  class="image-left"/>
                  </div>
              </div>
              <div class="dotted-vertical row-span-2 col-span-1">

                <div class="img-shadow">
                  <img :src="require(`~/assets/images/${item.imageRight}`)" :alt="`${item.header} graphic`"  class="image-right"/>
                </div>

                <div class="content-right">
                  <h4 class="subheader"> {{ item.subhead }}</h4>
                  <h2 class="h1-style"> {{ item.header }}</h2>
                  <p>{{ item.description }}</p>
                  <a class="btn-primary" v-if="item.url" no-prefetch :href="`${item.url}`">{{ item.linkText }}</a>
                </div>

              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
</template>

<script lang="ts">

export default {
	name: 'TwoImageWithText',
	props: {
		items: {
			type: Array
		}

	},

}
</script>



<style lang="scss">
.img-shadow {
 

  &:before {

  }
}

img {
  


  &:before {
  
  }
}

.image-left {
  width: 100%;
  max-width: 600px;
}

.image-right {
  width: 100%;
  max-width: 500px;
  margin-right: 0;
  right:0;
  position: absolute;
}


.content-right {
    display: block;
    position: relative;
    bottom: 12%;
    z-index: 1;
    left: 50%;
    position: absolute;
    background: $white;
    padding: 20px 60px;

}

.dotted-vertical {

     &:before {
        content: "";
        display: block;
        position: absolute;
        z-index: 1;
        top: 0;
        right: 45%;
        bottom: 0;
        border: 1px solid;
        border-width: 0 0 0 2px;
    }
}
</style>
