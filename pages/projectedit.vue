<template>
  <section class="section">
    <div class="container" style="flex-direction: column;justify-content: flex-start;">
      <EditProject :title="title"/>
    </div>
  </section>
</template>

<script>
import EditProject from '~/components/EditProject'


export default {
  name: 'projectedit',
  props: ['title'],
  middleware: 'auth',
  components: {
    EditProject,
  },
}
</script>

<style>
.back-part {
    background: rgba(104, 100, 100, 0.822);
    height: 50px;
}
</style>