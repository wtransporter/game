<template>
    <li v-for="message in logMessages" :key="message">
        <span
            :class="{
                'player': message.who === 'player',
                'opponent': message.who === 'opponent'
            }"
        >
            {{ message.who === 'player' ? 'Player' : 'Opponent'}}
        </span>
        <span v-if="message.type === 'heal'">
            healed himself 
            <span class="heal">
                with {{ message.value }} HP
            </span>
        </span>
        <span v-else>
            hit and made
            <span class="damage">
                {{ message.value }} damage
            </span>
        </span>
    </li>
</template>

<script>
    export default {
        inject: ['logMessages'],
    }
</script>

<style scoped>
    li {
        margin: 0;
        padding: 0;
    }

    .player_damage {
        color: red;
    }
    .player {
        color: rgb(235, 131, 13);
        font-weight: bold;
    }
    .opponent {
        color: rgb(74, 10, 179);
        font-weight: bold;
    }

    .heal {
        color: rgb(6, 163, 27);
        font-weight: bold;
    }

    .damage {
        color: rgb(235, 57, 13);
        font-weight: bold;
    }
</style>