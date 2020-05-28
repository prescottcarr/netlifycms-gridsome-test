<template>
  <Layout :show-logo="false">

    <div v-html="$page.posts.title" />

  </Layout>
</template>

<page-query>
query {
  posts: allPage {
      title
  }
}
</page-query>

<script>

export default {

  metaInfo: {
    title: 'About'
  }
}
</script>
