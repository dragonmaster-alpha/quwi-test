<template>
  <div class="Project-Edit-box">
    <span class="show-label">Name</span>
    <input class="input-name" placeholder="Please input project name" :value="title" />
    <button class="confirm-button" @click="goToDescPage"> OK </button>
  </div>
</template>
<script>
  export default {
    name: 'project-description',
    props: ['title'],
    data () {
      return {
        description: 'Project edit page'
      }
    },
    metaInfo () {
      return {
        title: this.title,
        meta: [
          { vmid: 'description', name: 'description', content: this.description }
        ]
      }
    },
    methods: {
        goToDescPage() {
            this.$router.push("/project")
        }
    }
  }
</script>
<style>
.confirm-button {
  background: rgb(68, 68, 124);
  color: white;
  text-align: center;
  padding: 4px 10px;
  font-size: 20px;
  letter-spacing: 1px;
  margin-left: 8px;
}
.input-name {
  padding: 4px 10px;
  font-size: 20px;
}
.show-label {
  margin-right: 40px;
  font-size: 20px;
}
.Project-Edit-box {
  display: flex;
  justify-content: flex-start;
  align-items: center;
  padding: 10px 20px;
  width: 600px;
  height: 120px;
  background: white;
  margin-bottom: 10px;
  border-radius: 8px;
}
</style>

