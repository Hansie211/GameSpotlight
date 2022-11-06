<template>
    <q-page class="flex col flex-center">
        <div id="page">
            <div class="row justify-center q-pb-md">
                <q-btn-toggle
                    glossy
                    v-model="slide"
                    :options="
                        games.map((game, index) => {
                            return { label: index + 1, value: game.name };
                        })
                    "
                />
            </div>
            <q-carousel animated v-model="slide" height="100%" infinite navigation arrows padding class="bg-primary shadow-1 rounded-borders">
                <q-carousel-slide v-for="game in games" :key="game.name" :name="game.name">
                    <game-card :gameInfo="game" />
                </q-carousel-slide>
            </q-carousel>
        </div>
    </q-page>
</template>

<script>
import { defineComponent, ref } from "vue";
import games from "src/data/games.json";
import GameCard from "src/components/game-card.vue";

export default defineComponent({
    components: { GameCard },
    name: "IndexPage",
    data() {
        return {
            games,
            slide: ref(games[0].name),
        };
    },
});
</script>
<style scoped>
#page {
    display: flex;
    flex-direction: column;
}
</style>
