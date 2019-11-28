<template>
  <section class="wrapper">
    <Sections v-if="wpData" :data="recipes" />
  </section>
</template>

<script>
import wpData from '@vue-wordpress/core/mixins/wpData'
import { FetchHookTypes } from '@vue-wordpress/core/types'

export default {
  name: 'MyCustomPage',
  mixins: [
    wpData(
      {
        slug: 'hello-world',
        type: 'posts',
        dataName: 'recipes'
      },
      FetchHookTypes.AsyncData
    )
  ],
  mounted() {
    // There we have access to 'sample-post-page' response!
    // eslint-disable-next-line no-console
    console.log(this.recipes)
  }
}
</script>
