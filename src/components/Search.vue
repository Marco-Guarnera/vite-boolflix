<script>
import axios from "axios";
import { store } from "../js/store.js";

export default {
    name: "Search",
    data: () => ({
        store,
        searchedInput: "",
        apiKey: "fd6c8d21185dd9ebbf4e3da065049532",
        moviesRequest: "https://api.themoviedb.org/3/search/movie",
        seriesRequest: "https://api.themoviedb.org/3/search/tv"
    }),
    methods: {
        getLists() {
            axios.all([
                axios.get(this.moviesRequest, {
                    params: {
                        api_key: this.apiKey,
                        query: this.searchedInput
                    }
                }),
                axios.get(this.seriesRequest, {
                    params: {
                        api_key: this.apiKey,
                        query: this.searchedInput
                    }
                })
            ]).then(axios.spread((moviesResponse, seriesResponse) => {
                this.store.moviesList = moviesResponse.data.results;
                this.store.seriesList = seriesResponse.data.results;
                this.searchedInput = "";
            })).catch(error => {
                console.log(error);
            });
        }
    }
}
</script>

<template>
    <!-- Search -->
    <form id="search" @submit.prevent="getLists">
        <input type="search" id="search-bar" class="form-control" placeholder="Cerca..." v-model.trim="searchedInput">
        <button id="search-button" class="btn"><font-awesome-icon icon="fa-solid fa-magnifying-glass" /></button>
    </form>
</template>

<style lang="scss" scoped>
@use "../scss/partials/color-variables.scss" as *;
@use "../scss/partials/mixins.scss" as *;

#search {
    @include flex(row, nowrap);
    gap: 0.25rem;

    * {
        border: 0;
    }

    #search-button {
        color: #FFF;
        background-color: $primary-color;
    }
}
</style>