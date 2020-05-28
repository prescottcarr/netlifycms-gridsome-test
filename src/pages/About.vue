<template>
  <Layout :show-logo="false">

    <h1>{{ $page.scott.title }}</h1>
    <p>{{ $page.scott.intro }}</p>

    <div v-for="person in $page.scott.team">
      <h3>{{ person.name }}</h3>
      <p>{{ person.position }}</p>
      <g-image :src="person.photo" width="100" height="100" fit="contain"/>
    </div>

  </Layout>
</template>


<page-query>
  query {
    scott (path:"/content/scott/about/") {
      title
      intro
      team {
        name
        position
        photo (width: 100, height: 100, quality: 90)
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
