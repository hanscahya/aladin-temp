<template lang="pug">
  div.wrapper-container
    b-img.bg-img.lg(:src="require('@/assets/bg-lg.jpg')")

    div.wrapper
      b-img.bg-img.sm(:src="require('@/assets/bg-sm.png')")
      b-img.logo(:src="require('@/assets/logo.png')")
      b-img.header-text(:src="lang === 'en' ? header_text_en : header_text_id")

      div.paragraph
        div
          p {{ lang === 'en' ? p1_en : p1_id }}
          p {{ lang === 'en' ? p2_en : p2_id }}
        div
          p {{ lang === 'en' ? p3_en : p3_id }}
          p {{ lang === 'en' ? p4_en : p4_id }}

      div.changeLanguage
        div(@click="changeLanguage('en')" :class="{ active: lang === 'en' }") EN
        div(@click="changeLanguage('id')" :class="{ active: lang === 'id' }") ID
      
      div.app-link
        span {{ lang === 'en' ? "Coming soon on" : "Segera hadir di" }}
        div.images
          b-img(:src="require('@/assets/app-store.png')")
          b-img(:src="require('@/assets/google-play.png')")
</template>

<script>
export default {
  data () {
    return {
      lang: 'id',

      header_text_en: require('@/assets/header-text-en.png'),
      header_text_id: require('@/assets/header-text-id.png'),

      p1_en: "Introducing Aladin: a next-gen, digital-first Sharia finance platform for the modern Indonesian.",
      p2_en: "Aladin was built with a simple purpose in mind - to create new opportunities for you to connect with the values you believe in, the passions that inspire you and the peers you care about.",
      p3_en: "Stay tuned for unparalleled access to smart money management tools, always-on customised promos at your favourite stores and new ways to give back to the community.",
      p4_en: "Are you ready?",

      p1_id: "Memperkenalkan Aladin: platform keuangan syariah generasi baru dan pertama untuk masyarakat Indonesia modern.",
      p2_id: "Aladin dibangun dengan sebuah tujuan sederhana, yaitu membuka kesempatanmu untuk terhubung dengan nilai-nilai yang kamu yakini, semangat yang menginspirasi, dan rekan-rekan yang kamu sayangi.",
      p3_id: "Nantikan sebuah akses tanpa batas kepada sebuah sarana manajemen keuangan pintar, promosi tiada henti yang disesuaikan dengan kebutuhanmu di gerai favoritmu, dan juga platform yang bisa membuatmu memberikan manfaat lebih bagi komunitasmu dan bagi orang banyak",
      p4_id: "Apakah kamu siap?",
    }
  },

  methods: {
    changeLanguage (lang) {
      this.lang = lang
    }
  }
}
</script>

<style lang="css" scoped>
.wrapper-container {
  display: flex;
  justify-content: center;
  align-items: center;

  position: relative;
  width: 100vw;
}
.wrapper-container .bg-img {
  width: 100vw;
  object-fit: cover;
  object-position: center;
}
@media screen and (max-width: 576px) {
  .wrapper-container .bg-img.sm {
    display: block;
    position: absolute;
    z-index: 0;
    opacity: 0.8;
  }
  .wrapper-container .bg-img.lg {
    display: none;
  }
}
@media screen and (min-width: 768px) {
  .wrapper-container .bg-img.sm {
    display: none;
  }
  .wrapper-container .bg-img.lg {
    display: block;
    height: 100vh;
  }
}

.wrapper {
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;

  display: flex;
  flex-direction: column;
  align-items: center;
}
@media screen and (max-width: 576px) {
  .wrapper {
    background-color: #00f3af;
    height: fit-content;
  }
}

.logo {
  width: 250px;
  z-index: 1;
}

.header-text {
  width: 300px;
  z-index: 1;
  margin-top: 50px;
}

.paragraph {
  display: flex;
  margin-top: 30px;
  width: 90%;
  z-index: 1;
}
.paragraph > div {
  padding: 1rem;
}
@media screen and (max-width: 576px) {
  .paragraph {
    flex-direction: column;
  }
}
@media screen and (min-width: 768px) {
  .paragraph {
    width: 50%;
  }
  .paragraph > div {
    width: 50%;
  }
}

.changeLanguage {
  display: flex;
  font-size: 10px;
  z-index: 100;
}
.changeLanguage > div {
  padding: 2px 10px;
  cursor: pointer;
}
.changeLanguage > div.active {
  font-weight: 900;
}
.changeLanguage > div:first-child {
  border-right: 0.5px solid #0006;
}

.app-link {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;

  margin-top: 50px;
  margin-bottom: 50px;

  z-index: 1;
}
.app-link span {
  font-size: 16px;
  font-weight: 600;
}
.app-link .images {
  display: flex;
  justify-content: center;
  align-items: center;
}
.app-link > .images > img {
  margin: 10px;
  width: 130px;
  object-fit: contain;
}
@media screen and (min-width: 768px) {
  .app-link {
    width: 300px;

    margin-top: 0px;
    margin-bottom: 0px;

    position: absolute;
    bottom: 0;
    right: 20px;
  }
}
</style>
