<template>
  <Layout :show-logo="false">

    <h1>{{ $page.about.title }}</h1>

  </Layout>
</template>


<page-query>
query ($id: ID!) {
  about(id: $id) {
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
