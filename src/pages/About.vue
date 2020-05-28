<template>
  <Layout :show-logo="false">

    <h1>{{ $page.scott.title }}</h1>

  </Layout>
</template>


<page-query>
  query {
    scott (id: "334e01214a76ac47cfc1f8dbcd39d1f9")  {
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
