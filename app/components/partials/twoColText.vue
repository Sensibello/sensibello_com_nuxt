<template>
    <div class="intro-text border-bottom">
      <div class="container mx-auto">
        <div class="py-24 md:py-36 mx-auto flex flex-wrap flex-col md:flex-row items-center">
          <div class="flex flex-col w-full justify-center lg:items-start overflow-y-hidden">
            <!-- <div v-html="$md.render(welcomeText)" class="home__welcome markdown" /> -->
            <div class="grid grid-cols-1 md:grid-cols-2" v-for="item in items" :key="item.name">
              <div class="row-span-3 col-span-1">
                <h1> {{ item.header }}</h1>
              </div>
              <div class="row-span-2 col-span-1">
                <p class="text-block">{{ item.description }}</p>
                <a class="btn-white" v-if="item.url" no-prefetch :href="`${item.url}`">{{ item.linkText }}</a>

              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
</template>

<script lang="ts">

export default {
  name: 'TwoColText',
	props: {
		items: {
			type: Array
		},
  },

  data() {
    return {
    };
  },
 
} 
</script>

<style lang="scss">

</style>
