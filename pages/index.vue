<template>
  <main style="width: 100%;">
    <section class="intro">
      <h1 class="intro__title text-xs-center">Get the latest tech news!</h1>
    </section>
    <section class="featured">
      <v-container
        grid-list-xl
        fluid>
        <v-layout
          row
          wrap>
          <post-preview
            v-for="post in getLoadedPosts.slice(0,6)"
            :key="post.id"
            :id="post.id"
            :thumbnail="post.thumbnail"
            :title="post.title"
            :preview-text="post.description"/>
        </v-layout>
      </v-container>
    </section>
  </main>
</template>

<script>
import PostPreview from '../components/Posts/PostPreview'

export default {
  components: { PostPreview },
  computed: {
    getLoadedPosts() {
      return this.$store.getters.getLoadedPosts
    }
  },
  head: {
    title: 'Latest tech news / Habr'
  }
}
</script>
