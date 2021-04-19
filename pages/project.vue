<template>
  <section class="section">
    <div class="container" style="flex-direction: column;justify-content: flex-start;">
      <label class="P-Title">Project Lists</label>
      <ProjectDesc title="Udimi" status="Active"/>
      <ProjectDesc title="Quwi Android" status="Active"/>
    </div>
  </section>
</template>

<script>
import ProjectDesc from '~/components/ProjectDesc'


export default {
  middleware: 'auth',
  components: {
    ProjectDesc,
  },
  data () {
    return {
      title: 'Udimi',
      status: 'Active'
    }
  }
}
</script>

<style>
.P-Title {
  font-size: 48px;
  margin-bottom: 20px;
  font-weight: bold;
  color: crimson;
}
</style>