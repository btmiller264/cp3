<template>
    <div class='wrapper'>
        <h1>Round of 16</h1>
        <div class='r16' v-for="round in rounds" :key="round.id">
            <div class='matchup'>
                <h2>First Round</h2>
                <div class='round'>
                    <div class='first'>
                        <h3>{{round.first.home}} - {{round.first.homeScore}}</h3>
                        <h3>{{round.first.away}} - {{round.first.awayScore}}</h3>
                    </div>
                </div>
                <h2>Second Round</h2>
                <div class='round'>
                    <div class='first'>
                        <h3>{{round.second.home}} - {{round.second.homeScore}}</h3>
                        <h3>{{round.second.away}} - {{round.second.awayScore}}</h3>
                    </div>
                </div>
            </div>
            <div class='message'>
                <p>{{round.message}}</p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "GameList",
    props: {
        rounds: Array
    },
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

    .r16 {
        width: 85%;
        border: solid white 1px;
        margin: 25px;
    }

    .matchup {
        display: flex;
        justify-content: center;
        align-items: flex-start;
        flex-flow: column;
        width: 100%;
        flex: 1;
        padding: 5px;
        margin: 10px;
    }

    .round {
        display: flex;
        justify-content: center;
        align-items: flex-start;
        flex-flow: column;
        width: 50%;
    }

    .first {
        display: flex;
        justify-content: center;
        align-items: flex-end;
        flex-flow: column;
        width: 100%;
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

    .r16 {
        width: 90%;
        border: solid white 1px;
        margin: 25px;
    }

    .matchup {
        display: flex;
        justify-content: center;
        align-items: flex-start;
        flex-flow: column;
        width: 100%;
        flex: 1;
        padding: 5px;
        margin: 10px;
    }

    .round {
        display: flex;
        justify-content: center;
        align-items: flex-start;
        flex-flow: column;
        width: 75%;
    }

    .first {
        display: flex;
        justify-content: center;
        align-items: flex-end;
        flex-flow: column;
        width: 80%;
    }

    .first h3 {
        font-size: 1.3em;
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

    .r16 {
        width: 90%;
        border: solid white 1px;
        margin: 25px;
    }

    .matchup {
        display: flex;
        justify-content: center;
        align-items: flex-start;
        flex-flow: column;
        width: 100%;
        flex: 1;
        padding: 5px;
        margin: 10px;
    }

    .matchup h2 {
        font-size: 1.5em;
    }

    .round {
        display: flex;
        justify-content: center;
        align-items: flex-start;
        flex-flow: column;
        width: 75%;
    }

    .first {
        display: flex;
        justify-content: center;
        align-items: flex-end;
        flex-flow: column;
        width: 100%;
    }

    .first h3 {
        font-size: 1em;
    }
 }

</style>