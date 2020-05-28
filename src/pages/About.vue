<template>
  <Layout :show-logo="false">

    <div v-html="$static.post.title" />

  </Layout>
</template>

<static-query>
  query {
    post {
      title
    }
  }
</static-query>

<script>

export default {

  metaInfo: {
    title: 'About'
  }
}
</script>
