<template>
  <Layout :show-logo="false">

    <div v-html="$static.page.title" />

  </Layout>
</template>

<static-query>
  query ($id: ID!) {
    page(id: $id) {
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
