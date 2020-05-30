<template>
  <Layout :show-logo="false">

    <h1>{{ $page.section.title }}</h1>
    <p>{{ $page.section.short}}</p>

    <div v-for="person in $page.section.locations">
      <h3>{{ person.name }}</h3>
      <p>{{ person.address }}</p>
    </div>

  </Layout>
</template>


<page-query>
  query {
    section (path:"/content/section/locations/") {
      title
      intro
      locations {
        name
        address
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
