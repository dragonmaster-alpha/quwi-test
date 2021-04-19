<template>
  <nav class="navbar is-light">
    <div class="container">
      <div class="navbar-brand">
        <nuxt-link class="navbar-item" to="/"><img src="../static/quwi-logo.png" /></nuxt-link>
        <button class="button navbar-burger">
          <span></span>
          <span></span>
          <span></span>
        </button>
      </div>
      <div class="navbar-menu">
        <div class="navbar-end">
          <div class="navbar-item has-dropdown is-hoverable" v-if="isAuthenticated">
            <a class="navbar-link">
            <img :src="`${ loggedInUser.avatar_url }`" style="padding-right: 5px" v-if="loggedInUser.avatar_url" />
            <img src="../static/quwi-logo.png" style="padding-right: 5px" v-else />
              {{ loggedInUser.name }}
            </a>
            <div class="navbar-dropdown">
                <nuxt-link class="navbar-item" to="/project">Projects</nuxt-link>
                <nuxt-link class="navbar-item" to="/profile">My Profile</nuxt-link>
                <hr class="navbar-divider"/>
                <a class="navbar-item"  @click="logout">Logout</a>
            </div>
          </div>
          <template v-else>
            <nuxt-link class="navbar-item" to="/register">Register</nuxt-link>
            <nuxt-link class="navbar-item" to="/login">Log In</nuxt-link>
          </template>
        </div>
      </div>
    </div>
  </nav>
</template>

<script>
import { mapGetters } from 'vuex'

export default {
  computed: {
    ...mapGetters(['isAuthenticated', 'loggedInUser'])
  },
  methods: {
    async logout() {
      await this.$auth.logout();
    },
  },
}
</script>