<template>
  <Layout :show-logo="false">

    <div v-for="edge in $page.posts.edges" :key="edge.node.id">
      <h2>{{ edge.node.title }}</h2>
    </div>

  </Layout>
</template>

<page-query>
query {
  posts: allPage {
    edges {
      node {
        id
        title
      }
    }
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
