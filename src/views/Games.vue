<template>
    <div class='games'>
        <GameView :rounds="games"/>
    </div>
</template>

<script>
import GameView from "../components/GameView.vue"
export default {
  name: 'GamesView',
  components: {
    GameView
  },
  computed: {
    games() {
      return this.$root.$data.games;
    }
  }
}
</script>

<style>  
  .games {
    width: 100%;
    background-image: url("../images/clb.jpg");
    background-size: auto;
    height: auto;
  }
</style>