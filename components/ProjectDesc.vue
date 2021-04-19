<template>
  <div class="Project-Description-box" @click="linkToEditPage">
    <div class="Project-Info">
      <img src="../static/quwi-logo.png" class="Project-Logo"/>
      <span class="Project-title">{{title}}</span>
    </div>
    <p class="Project-Status">{{status}}</p>
    <div class="Project-Time-Line">
      <div class="Project-Time-Title">
        <span>time this week</span>
        <span>this month</span>
        <span>total</span>
      </div>
      <div class="Project-Time-Value">
        <span>00:00:00</span>
        <span>00:00:00</span>
        <span>00:00:00</span>
      </div>
    </div>
  </div>
</template>
<script>
  export default {
    name: 'project-description',
    props: ['title', 'status'],
    data () {
      return {
        description: 'Project detail page'
      }
    },
    metaInfo () {
      return {
        title: this.title,
        status: this.status, 
        meta: [
          { vmid: 'description', name: 'description', content: this.description }
        ]
      }
    },
    methods: {
      linkToEditPage() {
        this.$router.push({name:'projectedit', params: {title: this.title}})
      }
    }
  }
</script>
<style>
.Project-Time-Line {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: stretch;
}
.Project-Time-Title, .Project-Time-Value {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: flex-start;
}
.Project-Time-Title {
  margin-right: 20px;
}
.Project-Info {
  display: flex;
  justify-content: flex-start;
  align-items: center;
  width: 30%;

}
.Project-title {
  font-weight: 500;
}
.Project-Status{
  font-weight: 500;
  color: green;
}
.Project-Description-box {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px 20px;
  width: 600px;
  height: 120px;
  background: white;
  margin-bottom: 10px;
  border-radius: 8px;
  cursor: pointer;
}
.Project-Logo {
  width: 40px;
  height: 40px;
  margin-right: 20px;
}
</style>

