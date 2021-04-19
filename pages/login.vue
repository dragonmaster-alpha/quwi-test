<template>
  <section class="section">
    <div class="container">
      <div class="columns">
        <div class="column">
          <h2 class="title">LOGIN</h2>

          <Notification :message="error" v-if="error"/>

          <form method="post" @submit.prevent="login">
            <div class="field">
              <div class="control">
                <input
                  type="email"
                  class="input"
                  name="email"
                  v-model="email"
                  placeholder="Email"
                />
              </div>
            </div>
            <div class="field">
              <div class="control">
                <input
                  type="password"
                  class="input"
                  name="password"
                  v-model="password"
                  placeholder="Password"
                />
              </div>
            </div>
            <div class="control">
              <button type="submit" class="button common-btn-style">LOGIN</button>
            </div>
          </form>
          <div class="has-text-centered" style="margin-top: 20px">
            <p>
              Don't have an account? <nuxt-link to="/register">Register</nuxt-link>
            </p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
<style>
</style>
<script>
import Notification from '~/components/Notification'

export default {
  middleware: 'guest',
  components: {
    Notification,
  },

  data() {
    return {
      email: '',
      password: '',
      error: null
    }
  },

  methods: {
    async login() {
      try {
        await this.$auth.loginWith('local', {
          data: {
            email: this.email,
            password: this.password
          }
        })
        this.$router.push('/project')
      } catch (e) {
          console.log(e.response)
        this.error = e.response.data.first_errors.email ? e.response.data.first_errors.email  : e.response.data.first_errors.password;
      }
    }
  }
}
</script>