<!-- ./components/Posts.vue -->
<template>
  <section class="main-content">
    <div class="container">
      <h1 class="title has-text-centered">
        Recent Posts.
      </h1>
      <div class="columns is-multiline">
        <div class="column is-half" v-for="post in posts" :key="post.id">
          <div class="card">
           <header class="card-header">
            <p class="card-header-title">
              {{ post.title }}
            </p>
          </header>
          <div class="card-content">
            <div class="content">
              {{ post.summary }}
              <br>
              <small>
                by <strong>{{ post.author}}</strong>
                \\ {{ post.published }}
              </small>
            </div>
          </div>
          <footer class="card-footer">
            <nuxt-link :to="`/post/${post.id}`"
              class="card-footer-item">
              <span>Read More</span>
            </nuxt-link>
          </footer>
        </div>
      </div>
    </div>
  </div>
</section>
</template>

<script>
  import posts from '~/posts.json'

  export default {
    name: 'posts',
    data () {
      return { posts }
    }
  }
</script>

<style scoped>
.card{
  border-radius: 0.5em;
}
.card-footer{
  padding: 15px;
}
.card-footer a {
  /*color: #213999;*/
  color: #d04c3f;
  font-weight: 500;
  -webkit-transition: color 0.2s;
  transition: color 0.2s;
  transition: transform 0.2s;
  display: inline-block;
  text-decoration: none;
  position: relative;
  padding: 5px;
  text-align: center;
}
.card-footer a:hover {
  color: #7a7a7a;
}
.card-footer a::before,
.card-footer a::after {
  position: absolute;
  top: 0;
  font-weight: 100;
  font-size: 150%;
  line-height: 1;
  opacity: 0;
  -webkit-transition: opacity 0.2s, -webkit-transform 0.2s;
  transition: opacity 0.2s, transform 0.2s;
}
.card-footer a::before {
  left: -0.1em;
  content: '[';
  padding: 5px 2px;
  -webkit-transform: translateX(-100%);
  transform: translateX(-100%);
}
.card-footer a::after {
  right: -0.1em;
  content: ']';
  padding: 5px 2px;
  -webkit-transform: translateX(100%);
  transform: translateX(100%);
}
.card-footer a:hover::before,
.card-footer a:hover::after {
  opacity: 1;
  -webkit-transform: translateX(0);
  transform: translateX(0);
}

</style>
