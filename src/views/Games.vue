<template>
    <div class='games'>
        <GameView :rounds="games"/>
        <div class="QF">
          <h1>Quarter-Final Matchup Creater</h1>
            <form> <fieldset>
                <legend>Create your matchup for the Quarter-Finals! Enter home team, away team, and date.</legend>
                <input placeholder="Home Team" v-model="home">
                <input placeholder="Away Team" v-model="away">
                <input placeholder="Date" v-model="date">
                <br><br>
                <button type="button" class="auto" @click="create(home, away, date)">Create Game</button>
                </fieldset>
            </form>

            <QFView :games="qfGames"/>
        </div>
    </div>

</template>

<script>
import GameView from "../components/GameView.vue"
import QFView from '../components/QFView.vue'
export default {
  name: 'GamesView',
  components: {
    GameView,
    QFView
  },
  data: function() {
    return {
      gameCount: 0,
    }
  },
  computed: {
    games() {
      return this.$root.$data.games;
    },
    qfGames() {
      return this.$root.$data.quarterFinals;
    }
  },
  methods: {
    create(home, away, date) {
      if (home != "" && away != "" && date != "") {
        var game = {
          id: this.gameCount++,
          home: home,
          away: away,
          date: date,
        };
        this.$root.$data.quarterFinals.push(game);
      }
    },
  }
}
</script>

<style>  
  .games {
    width: 100%;
    background-image: url("../images/clb.jpg");
    background-size: auto;
    height: auto;
    color:white;
  }

  form input {
    margin: 0 10px 0 10px;
  }
</style>