<template lang="html">
  <li class="media" v-if="post.user">
    <a target="_blank" :href="`/posts/${post['.key']}`" class="icon is-small">
      <span v-html="formattedPost"/>
    </a>
  </li>
</template>

<script>
import h from 'htmlspecialchars'
import { link } from 'autolinker'

  export default {
    props: {
      post: Object
    },
    computed: {
      formattedPost() {
        return link(h(this.post.body))
      }
    }
  }
</script>

<style lang="css">
</style>
