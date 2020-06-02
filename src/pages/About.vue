<template>
  <Layout>

    <h1>{{ $page.section.title }}</h1>
    <vue-markdown>{{ $page.section.intro }}</vue-markdown>
    <div v-for="person in $page.section.team">
      <h3>{{ person.name }}</h3>
      <p>{{ person.position }}</p>
      <g-image :src="person.photo" width="100" height="100" fit="contain"/>
    </div>

  </Layout>
</template>

<page-query>
  query {
    section (path:"/content/section/about/") {
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
import VueMarkdown from 'vue-markdown'

export default {
  components: {
    VueMarkdown
  },
  metaInfo: {
    title: 'About'
  }
}
</script>
