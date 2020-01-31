<template>
  <div class="container">

    <header></header>
    <div class="sub-header"></div>

    <div class="content">

      <div class="sidebar">
        <div style="background: white">
          <p v-for="i in 55" style="margin-bottom: 25px"> Hello {{i}}</p>
        </div>
      </div>
      <div class="map"></div>

    </div>
  </div>
</template>

<script>
import Logo from '~/components/Logo.vue'

export default {
  components: {
    Logo
  }
}
</script>

<style>


html,
body,
#__nuxt,
#__layout {
  height: 100%;
  margin: 0;
}

.container {
  margin: 0 auto;
  height: 100%;
  min-height: 100%;
  display: flex;
  flex-direction: column;
}
  header {
    background: antiquewhite;
    height: 50px;
    width: 100%;
  }

  .sub-header {
    background: #fa8681;
    height: 50px;
    width: 100%;
  }
  .content {
    display: flex;
    background: #78faeb;
    flex: 1;
    position: relative;
    overflow: hidden;
  }

  .sidebar {
    width: 550px;
    overflow: auto;
  }

  .map {
    width: 100%;
    background: orange;
  }

  @media (max-width: 768px) {

    .map {
      width: 100%;
      height: 100%;
      background: orange;
      position: absolute;
      top: 0;
      left: 0;
    }

    .sidebar {
      z-index: 1;
      width: 100%;
      padding-top: 500px;
    }
  }
</style>
