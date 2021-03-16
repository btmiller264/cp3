<template>
  <div class="groups">
    <TeamView :teams="groups"/>
  </div>
</template>

<script>
import TeamView from "../components/TeamView.vue"
export default {
  name: 'TeamsView',
  components: {
    TeamView
  },
  computed: {
    groups() {
      return this.$root.$data.teams;
    }
  }
}
</script>

<style>  
  .groups {
    width: 100%;
    background-image: url("../images/clb.jpg");
    background-size: auto;
    height: auto;
  }
</style>
