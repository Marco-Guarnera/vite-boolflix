<script>
import SeriesListItem from "./SeriesListItem.vue";
import { store } from "../js/store.js";

export default {
    name: "SeriesList",
    components: {
        SeriesListItem
    },
    data: () => ({
        store
    })
}
</script>

<template>
    <h2>Serie TV</h2>
    <!-- Series List -->
    <ul id="series-list">
        <!-- Series List Item -->
        <SeriesListItem v-for="item in store.seriesList" :key="item.id" :title="item.name"
            :original-title="item.original_name" :original-language="item.original_language"
            :vote-average="item.vote_average" :poster="item.poster_path" />
    </ul>
</template>

<style lang="scss" scoped></style>