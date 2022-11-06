<template>
    <div>
        <div id="box">
            <div id="title-box">
                <q-img id="backdrop" :src="gameInfo.backdrop" />
                <div id="title">{{ gameInfo.name }}</div>
            </div>
            <iframe id="trailer" width="560" height="315" :src="gameInfo.trailer" :title="gameInfo.name" frameborder="0" allow="autoplay; clipboard-write; encrypted-media; gyroscope;" allowfullscreen></iframe>
            <div id="text-row">
                <q-img id="cover" :src="gameInfo.cover" />
                <div id="description">
                    {{ gameInfo.description }}
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
    name: "GameCard",
    props: {
        gameInfo: {
            type: Object,
            default: () => {},
        },
    },
});
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Nunito:wght@600;800&display=swap");

#box {
    width: 1000px;
    background-color: lightgray;
    border-radius: 20px;
    padding: 20px;
    display: flex;
    flex-direction: column;
    align-items: center;
}

#title-box {
    position: relative;
    width: 100%;
    margin-bottom: 40px;
}

#title {
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;

    opacity: 0.1;
    background-color: rgba(255, 255, 255, 0.6);

    font-size: 3em;
    font-weight: bold;
    color: rgb(50, 50, 50);
    font-family: "Nunito", sans-serif;
    padding-left: 10px;
}

#title-box:hover > #title {
    opacity: 1;
}

#trailer {
    margin-bottom: 40px;
}

#text-row {
    border: 5px solid black;
    border-radius: 10px;
    width: 100%;
    overflow: hidden;

    display: flex;
    flex-direction: row;
}

#cover {
    height: 100%;
    max-width: 300px;
}

#description {
    padding: 10px;
    color: black;
    white-space: pre-line;
}
</style>
