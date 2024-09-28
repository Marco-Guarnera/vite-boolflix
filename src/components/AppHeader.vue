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
        <!-- Navbar -->
        <nav id="navbar">
            <ul id="navbar-list" class="m-0 p-0">
                <li class="navbar-list-item"><a href="#"><h2>Boolflix</h2></a></li>
                <li class="navbar-list-item"><a href="#">Home</a></li>
                <li class="navbar-list-item"><a href="#">Film</a></li>
                <li class="navbar-list-item"><a href="#">Serie TV</a></li>
            </ul>
        </nav>
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
    @include flex(row, wrap);
    justify-content: space-between;
    align-items: center;
    padding: 0 1rem;

    #navbar-list {
        @include flex(row, nowrap);
        align-items: center;
        gap: 1rem;

        a {
            color: #FFF;

            h2 {
                color: $primary-color;
                margin: 0 1.5rem 0 0;
            }
        }
    }
}
</style>