<template lang="pug">
.container
  textarea(v-model="tweet")
  button(@click="post()")
    | post
  .list-group
    .list-item(v-for="t in tweetList")
      | {{t}}
</template>

<style lang="sass">
</style>

<script>
import { reverse } from 'lodash'

export default {
  data() {
    return {
      tweet: '',
      tweetList: []
    }
  },
  methods: {
    post() {
      this.tweetList.push(this.tweet)
      this.tweetList = reverse(this.tweetList)
      this.clear()
    },
    clear() {
      this.tweet = ''
    },
  }
}
</script>
