<template>
  <Layout :show-logo="false">

    <h1>{{ $page.section.title }}</h1>
    <p>{{ $page.section.short}}</p>


    <div>{{ $page.section.hours}}</div>
    <p>{{ $page.section.map.coordinates}}</p>
    <p>{{ $page.section.phone}}</p>
    <p>{{ $page.section.email}}</p>
    <p>{{ $page.section.address1}}</p>
    <p>{{ $page.section.address2}}</p>
    <p>{{ $page.section.district}}</p>
    <p>{{ $page.section.island}}</p>
    <p>{{ $page.section.country}}</p>
    <p>{{ $page.section.postal}}</p>


  </Layout>
</template>


<page-query>
  query {
    section (path:"/content/section/locations/") {
      title
      short
      hours
      map {
        coordinates
      }
      phone
      email
      address1
      address2
      district
      island
      country
      postal
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
