<template>
  <div class="trans">
    <!-- navigation -->
    <nav class="nav has-shadow">
      <div class="container">
        <div class="nav-left">
          <nuxt-link to="/" class="nav-item">
            Awesome JS SSR Blog!
          </nuxt-link>
          <nuxt-link active-class="is-active" to="/" class="nav-item is-tab" exact>Home</nuxt-link>
          <nuxt-link active-class="is-active" to="/about" class="nav-item is-tab" exact>About</nuxt-link>
        </div>
      </div>

    </nav>
    <!-- /navigation -->

    <!-- displays the page component -->
    <nuxt/>
    <foot></foot>

  </div>
</template>

<script>
import Foot from '../components/Footer.vue'
import AppLogo from '../components/AppLogo.vue'
export default {
  components: {
    Foot,
    AppLogo
  }
}
</script>

<style>

.main-content {
  /* margin: 30px 0;*/

  /* Sticky footer
    What we're doing here is setting the main area to 100 percent of the viewport's height,
    minus the height of the header and footer (20vh each). This will ensure that the
    layout takes up the full height of the screen, even when there's not much content.
  */
  min-height: calc(100vh - 20vh);
  padding: 30px 30px 0 30px;
}

.footer{

  /* Sticky footer  */
  width: 100%;
  height: 100px;
  bottom: 0;
}

/*footer {
  bottom: 0;
  left: 0;
  position: fixed;
  right: 0;
  z-index: 30;
}*/
</style>



