<template>
  <div>
    {{ post }}
  </div>
</template>

<script>
import postQuery from '~/graphql/queries/post/post'

export default {
  apollo: {
    post: {
      prefetch: true,
      query: postQuery,
      variables() {
        return { id: parseInt(this.$route.params.id) }
      },
    },
  },
}
</script>
