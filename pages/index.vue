<!-- ./pages/index.vue -->

<template>
  <div>
   <!--  <section class="hero is-medium is-dark is-bold">
      <img src="img/portfolio-bg.jpg" alt="codigo fuente">
      <div class="hero-body">
        <div class="container">
          <h1 class="title">
            Welcome to the JavaScript SSR Blog.
          </h1>
          <h2 class="subtitle">
            Hope you find something you like.
          </h2>
        </div>
      </div>
    </section> -->
    <section class="hero">
      <div class="hero-body">
        <div class="container">
          <h1 class="title" style="font-weight:500">
            Welcome to the JavaScript SSR Blog.
          </h1>
          <h2 class="subtitle">
            Hope you find something you like.
          </h2>
            <div class="imagen" >
              <img src="img/portfolio-bg.jpg" style="background:no-repeat fixed center;
              background-size: cover; width:100%;"
              alt="">
            </div>
        </div>
      </div>
    </section>

   <posts />

  </div>
</template>

<script>
  import Posts from '~/components/Posts.vue'
  export default {
    components: {
      Posts
    },
    head: {
      title: 'Home'
    }
  }
</script>

<style>
</style>

<!-- <style>
.container {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif; /* 1 */
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
 -->
