<template>
  <Layout :show-logo="false">

    <h1>{{ $page.section.title }}</h1>
    <p>{{ $page.section.short}}</p>

    <div>{{ $page.section.hours}}</div>
    <p>{{ $page.section.phone}}</p>
    <p>{{ $page.section.email}}</p>
    <p>{{ $page.section.address1}}</p>
    <p>{{ $page.section.address2}}</p>
    <p>{{ $page.section.district}}</p>
    <p>{{ $page.section.island}}</p>
    <p>{{ $page.section.country}}</p>
    <p>{{ $page.section.postal}}</p>

    <GmapMap
    :center="{lat:19.2985383, lng:-81.3676755}"
    :zoom="13"
    map-type-id="roadmap"
    style="width: 400px; height: 250px"
    >
    <GmapMarker
    :position="{lat:19.2985383, lng:-81.3676755}"
    :clickable="true"
    @click="websiteUrl"
    />
  </GmapMap>


  </Layout>
</template>


<page-query>
  query {
    section (path:"/content/section/contact/") {
      title
      short
      hours
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
    title: 'Contact Us'
  },
  methods: {
    websiteUrl: function(event) {
        window.open("https://www.google.com/maps/dir//Hew's+Cleaning+Services,+335+Dorcy+Dr,+George+Town,+Cayman+Islands/@19.2985383,-81.3676755,15z/data=!4m16!1m6!3m5!1s0x0:0x1da08c8686cc4f6e!2sHew's+Cleaning+Services!8m2!3d19.2985383!4d-81.3676755!4m8!1m0!1m5!1m1!1s0x8f258643fee1623d:0x1da08c8686cc4f6e!2m2!1d-81.3676755!2d19.2985383!3e2");
    }
  }
}
</script>
