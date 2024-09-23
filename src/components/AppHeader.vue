<script>
import Search from "./Search.vue";

export default {
    name: "AppHeader",
    components: {
        Search
    }
}
</script>

<template>
    <!-- Header -->
    <header>
        <h2>AppHeader</h2>
        <!-- Search -->
        <Search />
    </header>
</template>

<style lang="scss" scoped>
@use "../scss/partials/color-variables.scss" as *;
@use "../scss/partials/mixins.scss" as *;

header {
    height: 75px;
    background-color: $background-color;
    border: 2px dashed #F24822;
    @include flex(row, wrap);
    justify-content: space-between;
    align-items: center;
    padding: 0 1rem;

    h2 {
        color: #FFF;
        margin: 0;
    }
}
</style>