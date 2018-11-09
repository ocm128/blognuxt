<!-- ./pages/post/_id/index.vue -->
<template>
  <div class="main-content">
    <div class="container">
      <h2 class="title is-2">{{ post.title }}</h2>
      <div v-html="post.content"></div>
      <br>
      <h4 class="title is-5 is-marginless">by <strong>{{ post.author }}
        </strong> at <strong>{{ post.published }}</strong></h4>
    </div>
  </div>
</template>

<script>
  // import posts saved JSON data and place them in a file in the app root folder.
  import posts from '~/posts.json'

  export default {

    // It checks if the route parameter passed is a number
    // If it returns false, Nuxt.js will automatically load the 404 error page
    validate ({ params }) {
      return /^\d+$/.test(params.id)
    },

    // Used to fetch data and render it on the server-side before sending a
    // response to the browser.
    asyncData ({ params }, callback) {
      let post = posts.find(post => post.id === parseInt(params.id))
      if (post) {
        callback(null, { post })
      } else {
        callback({ statusCode: 404, message: 'Post not found' })
      }
    },

    // Set the page’s headers. In this case, we are changing the page title
    // to the title of the post, and adding the post summary as a meta
    // description for the page.
    head () {
      return {
        title: this.post.title,
        meta: [
          {
            hid: 'description',
            name: 'description',
            content: this.post.summary
          }
        ]
      }
    }
  }
</script>
