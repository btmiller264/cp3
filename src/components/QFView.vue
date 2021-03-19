<template>
    <div class='wrapper'>
        <div class="QFGames">
            <h1>Quarter-Finals</h1>
            <div class="QFGame" v-for="game in games" :key="game.id">
                <div class='matchup'>
                    <div class='title'>
                        <h2>First Round</h2>
                    </div>
                    <div class='round'>
                        <div class='first'>
                            <h3>{{game.home}} - -</h3>
                            <h3>{{game.away}} - -</h3>
                        </div>
                    </div>
                    <div class='title'>
                        <h2>Second Round</h2>
                    </div>
                    <div class='round'>
                        <div class='first'>
                            <h3>{{game.away}} - -</h3>
                            <h3>{{game.home}} - -</h3>
                        </div>
                    </div>
                </div>
                <div class='message'>
                    <p>To be played on {{game.date}}</p>
                </div>
                <div class="buttons">
                    <button type="button" class="auto" @click="edit()">Edit Game</button>
                    <button type="button" class="auto" @click="deleteGame(game)">Delete Game</button>
                </div>
                <div v-if="getEdit !== false">
                    <form> <fieldset>
                        <legend>Game Editor</legend>
                        <input placeholder="Home Team" v-model="home">
                        <input placeholder="Away Team" v-model="away">
                        <input placeholder="Date" v-model="date">
                        <br><br>
                        <button type="button" class="auto" @click="submitEdit(game, home, away, date)">Submit Edit</button>
                        </fieldset>
                    </form>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "QFGameList",
    props: {
        games: Array
    },
    data: function() {
        return {
            editGame: false,
        }
    },
    methods: {
        edit() {
            this.editGame = !this.editGame;
        },
        submitEdit(game, home, away, date) {
            if (home != "") {
                game.home = home;
            }
            if (away != "") {
                game.away = away;
            }
            if (date != "") {
                game.date = date;
            }
            this.editGame = false;
        },
        deleteGame(game) {
            var index = this.$root.$data.quarterFinals.indexOf(game);
            this.$root.$data.quarterFinals.splice(index, 1);
        }
    },
    computed: {
        getEdit() {
            return this.editGame;
        }
    }
}
</script>

<style>
@media only screen and (min-width: 961px) {
    .wrapper {
        color: white;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-flow: column;
        width: 100%;
        height: auto;
        flex: 1;
    }

    .QFGames {
        width: 85%;
        margin: 25px;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-flow: column;
    }

    .QFGame {
        width: 100%;
        border: solid white 1px;
        margin: 25px;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-flow: column;
    }

    .matchup {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-flow: column;
        width: 100%;
        flex: 1;
        padding: 5px;
        margin: 10px;
    }

    .title {
        width: 75%;
        border: solid 1px white;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .round {
        display: flex;
        justify-content: center;
        align-items: flex-start;
        flex-flow: column;
        width: 100%;
    }

    .first {
        display: flex;
        justify-content: center;
        align-items: flex-end;
        flex-flow: column;
        width: 50%;
    }

    .buttons button {
        margin: 0 10px 0 10px;
    }
}

@media only screen and (min-width: 427px) and (max-width: 960px) { 
    .wrapper {
        color: white;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-flow: column;
        width: 100%;
        height: auto;
        flex: 1;
    }

    .QFGames {
        width: 85%;
        margin: 25px;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-flow: column;
    }

    .QFGame {
        width: 100%;
        border: solid white 1px;
        margin: 25px;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-flow: column;
    }

    .matchup {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-flow: column;
        width: 100%;
        flex: 1;
        padding: 5px;
        margin: 10px;
    }

    .title {
        width: 75%;
        border: solid 1px white;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .title h2 {
        font-size: 1.5em;
    }

    .round {
        display: flex;
        justify-content: center;
        align-items: flex-start;
        flex-flow: column;
        width: 100%;
    }

    .first {
        display: flex;
        justify-content: center;
        align-items: flex-end;
        flex-flow: column;
        width: 50%;
    }

    .first h3 {
        font-size: 1em;
    }

    .buttons button {
        margin: 0 10px 0 10px;
    }
 }

 @media only screen and (max-width: 426px) {
     .wrapper {
        color: white;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-flow: column;
        width: 100%;
        height: auto;
        flex: 1;
    }

    .QFGames {
        width: 85%;
        margin: 25px;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-flow: column;
    }

    .QFGame {
        width: 100%;
        border: solid white 1px;
        margin: 25px;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-flow: column;
    }

    .matchup {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-flow: column;
        width: 100%;
        flex: 1;
        padding: 5px;
        margin: 10px;
    }

    .title {
        width: 75%;
        border: solid 1px white;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .title h2 {
        font-size: 1.5em;
    }

    .round {
        display: flex;
        justify-content: center;
        align-items: flex-start;
        flex-flow: column;
        width: 100%;
    }

    .first {
        display: flex;
        justify-content: center;
        align-items: flex-end;
        flex-flow: column;
        width: 75%;
    }

    .first h3 {
        font-size: 1em;
    }

    .buttons button {
        margin: 0 10px 0 10px;
    }
 }
</style>