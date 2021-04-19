<template>
  <section class="section">
    <div class="container">
      <h1 class="title">Nuxt Auth</h1>
    </div>
  </section>
</template>

<script>
import AppLogo from '~/components/AppLogo.vue'

export default {
  components: {
    AppLogo
  }
}
</script>

<style>
.container {
  min-height: calc(100vh - 148px);
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}
.title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif; /* 1 */
  display: block;
  font-weight: bold;
  font-size: 20px;
  color: #35495e;
  letter-spacing: 1px;
  text-align: left;
}
.big-title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif; /* 1 */
  display: block;
  font-weight: bold;
  font-size: 52px;
  color: #35495e;
  letter-spacing: 1px;
  text-align: center;
}
section {
  background: #eae9e9;
}

.common-btn-style{
    background: #534ab1;
    width: 50%;
    color: white;
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

