<template>
  <div class="container">
    {{ posts }}
  </div>
</template>

<script>
import postsQuery from '~/graphql/queries/post/posts'

export default {
  apollo: {
    posts: {
      prefetch: true,
      query: postsQuery,
      variables() {
        return { id: parseInt(this.$route.params.id) }
      },
    },
  },
}
</script>

<style></style>
