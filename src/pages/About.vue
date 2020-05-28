<template>
  <Layout :show-logo="false">

    <div v-html="$static.post.title" />

  </Layout>
</template>

<static-query>
  query ($id: ID!) {
    post(id: $id) {
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
