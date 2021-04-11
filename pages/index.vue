<template lang="pug">
  div.wrapper-container
    b-img.bg-img.lg(:src="require('@/assets/bg-lg.jpg')")

    div.wrapper
      b-img.bg-img.sm(:src="require('@/assets/bg-sm.png')")
      b-img.logo(:src="require('@/assets/logo.png')")
      b-img.header-text(:src="require('@/assets/header-text.png')")

      div.paragraph
        div
          p Introducing Aladin: a next-gen, digital-first Sharia finance platform for the modern Indonesian.
          p Aladin was built with a simple purpose in mind - to create new opportunities for you to connect with the values you believe in, the passions that inspire you and the peers you care about.
        div
          p Stay tuned for unparalleled access to smart money management tools, always-on customised promos at your favourite stores and new ways to give back to the community.
          p Are you ready?
      
      div.app-link
        span Coming soon on
        div.images
          b-img(src="https://i.imgur.com/jzgW7wU.png")
          b-img(src="https://i.imgur.com/3y4Iue7.png")
</template>

<script>
export default {}
</script>

<style lang="css" scoped>
.wrapper-container {
  display: flex;
  justify-content: center;
  align-items: center;

  position: relative;

  height: 100vh;
  width: 100vw;
}
.wrapper-container .bg-img {
  height: 100vh;
  width: 100vw;
  object-fit: cover;
  object-position: center bottom;
}
@media screen and (max-width: 576px) {
  .wrapper-container .bg-img.sm {
    display: block;
    position: absolute;
    z-index: 0;
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
  width: 350px;
  z-index: 1;
}

.paragraph {
  display: flex;
  margin-top: 50px;
  width: 90%;
  z-index: 1;
}
.paragraph > div {
  padding: 1rem;
}
@media screen and (min-width: 768px) {
  .paragraph {
    width: 50%;
  }
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
