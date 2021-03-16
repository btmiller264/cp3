<template>
    <div class='wrapper'>
        <div class='group' v-for="group in teams" :key="group.groupid">
            <h2>Group {{group.group}}</h2>
            <div class='teams'>
                <div v-for="team in group.clubs" :key="team.id">
                    <div class='team'>
                        <h3>{{team.club}}</h3>
                        <p>Location: {{team.location}}</p>
                        <p>League: {{team.league}}</p>
                        <p>Champions League Titles: {{team.titles}}</p>
                        <p v-if="team.wonBefore">Most Recent Win: {{team.mostRecentWin}}</p>
                        <p>Top Scorer: {{team.topScorer}}</p>
                        <p v-if="team.eliminated">Eliminated in group stage</p>
                        <p v-if="!team.eliminated">Advanced to Round of 16</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "TeamList",
    props: {
        teams: Array
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
    }

    .group {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-flow: column;
        width: 95%;
        border: solid white 1px;
        margin-top: 20px;
        margin-bottom: 20px;
        height: 100%;
    }

    .teams {
        display: flex;
        flex-flow: row;
        justify-content: space-evenly;
        align-items: stretch;
        width: 100%;
        border: solid white 1px;
        height: 100%;
    }

    .team {
        display: flex;
        justify-content: baseline;
        align-items: center;
        flex-flow: column;
        flex: 1;
        margin: 0 5px 0 5px;
        padding: 5px;
    }

    .team p {
        margin: 0;
        padding: 0;
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
    }

    .group {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-flow: column;
        width: 95%;
        border: solid white 1px;
        margin-top: 20px;
        margin-bottom: 20px;
        height: 100%;
    }

    .teams {
        display: flex;
        flex-flow: row ;
        justify-content: space-around;
        align-items: stretch;
        width: 100%;
        border: solid white 1px;
        height: 100%;
        flex: 1;
    }

    .team {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-flow: column;
        flex: 1;
        margin: 0 5px 0 5px;
        padding: 5px;
    }

    .team h3 {
        font-size: 1.3em;
    }

    .team p {
        margin: 0;
        padding: 0;
        font-size: 0.8em;
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
    }

    .group {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-flow: column;
        width: 95%;
        border: solid white 1px;
        margin-top: 20px;
        margin-bottom: 20px;
        height: 100%;
    }

    .teams {
        display: flex;
        flex-flow: column;
        justify-content: space-around;
        align-items: stretch;
        width: 100%;
        border: solid white 1px;
        height: 100%;
        flex: 1;
    }

    .team {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-flow: column;
        flex: 1;
        margin: 5px 0 5px 0;
        padding: 5px;
    }

    .team p {
        margin: 0;
        padding: 0;
    }
}

</style>