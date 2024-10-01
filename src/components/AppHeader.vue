<script>
import Search from "./Search.vue";

export default {
    name: "AppHeader",
    components: {
        Search
    },
    data: () => ({
        currentPage: 0,
        // Struttura dati
        pagesList: [
            {
                id: 1,
                name: "Home",
                url: "#"
            },

            {
                id: 2,
                name: "Film",
                url: "#"
            },

            {
                id: 3,
                name: "Serie TV",
                url: "#"
            }
        ]
    }),
    methods: {
        setActivePage(page) {
            if (page === this.currentPage) return "active-page";
        }
    }
}
</script>

<template>
    <!-- Header -->
    <header>
        <!-- Navbar -->
        <nav id="navbar">
            <ul id="navbar-list" class="m-0 p-0">
                <li class="navbar-list-item">
                    <a href="#"><h2>Boolflix</h2></a>
                </li>
                <li class="navbar-list-item" :class="setActivePage(i)" v-for="(item, i) in pagesList" :key="item.id">
                    <a :href="item.url" v-text="item.name"></a>
                </li>
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

        h2 {
            color: $primary-color;
            margin: 0 1.5rem 0 0;
        }

        .active-page a {
            cursor: default;
            color: #FFF;
        }

        :not(.active-page) a {
            color: #DDD;

            &:hover {
                color: #BBB;
            }
        }
    }
}
</style>