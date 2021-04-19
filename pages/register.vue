<template>
  <section class="section">
    <div class="container">
      <div class="columns">
        <div class="column">
          <h2 class="title">REGISTER</h2>

          <Notification :message="error" v-if="error"/>

          <form method="post" @submit.prevent="register">
            <div class="field">
              <div class="control">
                <input
                  type="text"
                  class="input"
                  name="username"
                  v-model="username"
                  placeholder="UserName"
                  required
                />
              </div>
            </div>
            <div class="field">
              <div class="control">
                <input
                  type="email"
                  class="input"
                  name="email"
                  v-model="email"
                  placeholder="Email"
                  required
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
                  required
                />
              </div>
            </div>
            <div class="control">
              <button type="submit" class="button common-btn-style">REGISTER</button>
            </div>
          </form>

          <div class="has-text-centered" style="margin-top: 20px">
            Already got an account? <nuxt-link to="/login">Login</nuxt-link>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import Notification from '~/components/Notification'

export default {
  middleware: 'guest',
  components: {
    Notification,
  },

  data() {
    return {
      username: '',
      email: '',
      password: '',
      error: null
    }
  },

  methods: {
    async register() {
      try {
        await this.$axios.post('auth/signup', {
          name: this.username,
          email: this.email,
          password: this.password
        })

        await this.$auth.loginWith('local', {
          data: {
          email: this.email,
          password: this.password
          },
        })

        this.$router.push('/project')
      } catch (e) {
        this.error = e.response.data.first_errors.email ? e.response.data.first_errors.email  : e.response.data.first_errors.password;
      }
    }
  }
}
</script>