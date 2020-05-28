<template>
  <Layout :show-logo="false">

    <h1>{{ $page.scott.title }}</h1>

  </Layout>
</template>


<page-query>
query ($id: ID!) {
  scott(id: $id) {
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
