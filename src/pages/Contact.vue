<template>
  <Layout>
    <div class="hero-image">
      <div class="hero-image__container">
        <g-image :src="$page.section.photo"/>
      </div>
      <div class="hero-text px-4">
        <h1 class="text-5xl font-bold mb-2 text-white">{{ $page.section.title }}</h1>
        <vue-markdown class="text-2xl mb-8 text-gray-200">{{ $page.section.short }}</vue-markdown>
      </div>
    </div>
    <div class="container mx-auto px-4">
      <div class="contact relative grid grid-cols-1 sm:grid-cols-2 gap-10">
        <div class="contact-box">
          <vue-markdown>{{ $page.section.hours }}</vue-markdown>
          <p>{{ $page.section.phone }}</p>
          <p>{{ $page.section.email }}</p>
          <p>{{ $page.section.address1 }}</p>
          <p>{{ $page.section.address2 }}</p>
          <p>{{ $page.section.district }}</p>
          <p>{{ $page.section.island }}</p>
          <p>{{ $page.section.country }}</p>
          <p>{{ $page.section.postal }}</p>
        </div>

        <div class="contact-box">
          <GmapMap
          :center="{lat:19.2985383, lng:-81.3676755}"
          :zoom="13"
          map-type-id="roadmap"
          style="width: 100%; height: 250px"
          >
          <GmapMarker
          :position="{lat:19.2985383, lng:-81.3676755}"
          :clickable="true"
          @click="websiteUrl"
          />
        </GmapMap>
        </div>
      </div>

    </div>
  </Layout>
</template>


<page-query>
  query {
    section (path:"/content/section/contact/") {
      title
      photo
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
import VueMarkdown from 'vue-markdown'

export default {

  metaInfo: {
    title: 'Contact Us'
  },
  components: {
    VueMarkdown
  },
  methods: {
    websiteUrl: function(event) {
        window.open("https://www.google.com/maps/dir//Hew's+Cleaning+Services,+335+Dorcy+Dr,+George+Town,+Cayman+Islands/@19.2985383,-81.3676755,15z/data=!4m16!1m6!3m5!1s0x0:0x1da08c8686cc4f6e!2sHew's+Cleaning+Services!8m2!3d19.2985383!4d-81.3676755!4m8!1m0!1m5!1m1!1s0x8f258643fee1623d:0x1da08c8686cc4f6e!2m2!1d-81.3676755!2d19.2985383!3e2");
    }
  }
}
</script>

<style>

.hero-image {
  min-height: 280px;
  position: relative;
  z-index: 1;
  background-color: #157e91;
  background-image: url("data:image/svg+xml,%3Csvg width='6' height='6' viewBox='0 0 6 6' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='%23f7f7f7' fill-opacity='0.4' fill-rule='evenodd'%3E%3Cpath d='M5 0h1L0 6V5zM6 5v1H5z'/%3E%3C/g%3E%3C/svg%3E");
}

.hero-image__container {
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
}

.hero-image__container:after {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
  z-index: 1;
  background: linear-gradient(45deg, #6a78d1, #00a4bd);
  opacity: .8;
}

.hero-image__container img {
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
  object-fit: cover;
  max-height: 100%;
  max-width: 100%;
  min-height: 100%;
  min-width: 100%;
}

.hero-text {
  position: absolute;
  display: flex;
  flex-direction: column;
  justify-content: center;
  width: 100%;
  height: 100%;
  align-items: center;
  z-index: 1;
}

.contact {
  top: -50px;
}

.contact-box {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  padding: 32px 40px;
  background-color: #fff;
  border: 1px solid #eaf0f6;
  z-index: 2;
}

</style>
