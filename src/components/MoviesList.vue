<script>
import MoviesListItem from "./MoviesListItem.vue";
import { store } from "../js/store.js";

export default {
    name: "MoviesList",
    components: {
        MoviesListItem
    },
    data: () => ({
        store
    })
}
</script>

<template>
    <h2>Film</h2>
    <!-- Movies List -->
    <ul id="movies-list">
        <!-- Movies List Item -->
        <MoviesListItem v-for="item in store.moviesList" :key="item.id" :title="item.title"
            :original-title="item.original_title" :original-language="item.original_language"
            :vote-average="item.vote_average" :poster="item.poster_path" />
    </ul>
</template>

<style lang="scss" scoped></style>