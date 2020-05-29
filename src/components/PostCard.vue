<template>

  <div class="max-w-sm rounded overflow-hidden shadow-lg">
    <g-image alt="Cover image" v-if="post.cover_image" class="w-full" :src="post.cover_image"/>
    <div class="px-6 py-4">
      <div class="font-bold text-xl mb-2" v-html="post.title"></div>
      <p class="text-gray-700 text-base" v-html="post.description"></p>
    </div>
    <div class="px-6 py-4">
      <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2">#photography</span>
      <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2">#travel</span>
      <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700">#winter</span>
    </div>
  </div>

</template>

<script>
import PostMeta from '~/components/PostMeta'
import PostTags from '~/components/PostTags'

export default {
  components: {
    PostMeta,
    PostTags
  },
  props: ['post'],
}
</script>

<style>

</style>
