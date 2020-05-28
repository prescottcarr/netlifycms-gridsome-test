<template>
  <Layout :show-logo="false">

    <h1>{{ $page.scott.title }}</h1>

  </Layout>
</template>


<page-query>
  query {
    scott (path: "/content/scott/about/")  {
      title
      team {
        name
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
