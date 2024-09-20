<script>
export default {
    name: "AppHeader"
}
</script>

<template>
    <!-- Header -->
    <header>
        <h2>AppHeader</h2>
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
    justify-content: center;
    align-items: center;

    h2 {
        color: #FFF;
    }
}
</style>