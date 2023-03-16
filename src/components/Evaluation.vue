// Evaluation.vue

<template>
    <div>
        <h1>Player Selection</h1>
        <button v-on:click="getPlayerList">Get List of Players</button>
        <div>{{playerList}}</div>
    </div>
</template>

<script>
    export default {
        name: 'playerToEvaluate',
        data() {
            return {
                playerList: []
            };
        },
        methods: {
            getPlayerList() {
                fetch("majorsbb.json")
                    .then(response => response.json())
                    .then(data => (this.playerList = data));
            }
        }
    };
</script>