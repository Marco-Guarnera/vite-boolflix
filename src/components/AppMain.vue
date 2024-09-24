<script>
import MoviesList from "./MoviesList.vue";
import SeriesList from "./SeriesList.vue";

export default {
    name: "AppMain",
    components: {
        MoviesList,
        SeriesList
    }
}
</script>

<template>
    <!-- Main -->
    <main>
        <h2>AppMain</h2>
        <!-- Movies List -->
        <MoviesList />
        <!-- Series List -->
        <SeriesList />
    </main>
</template>

<style lang="scss" scoped>
@use "../scss/partials/color-variables.scss" as *;
@use "../scss/partials/mixins.scss" as *;

main {
    min-height: calc(100vh - 75px);
    background-color: $background-color;
    border: 2px dashed #F24822;
    @include flex(row, wrap);
    justify-content: center;
    align-items: center;

    h2 {
        color: #FFF;
    }
}
</style>