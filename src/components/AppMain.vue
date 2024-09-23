<script>
import List from "./List.vue";

export default {
    name: "AppMain",
    components: {
        List
    }
}
</script>

<template>
    <!-- Main -->
    <main>
        <h2>AppMain</h2>
        <!-- List -->
        <List />
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