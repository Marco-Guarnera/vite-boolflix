<script>
import axios from "axios";
import { store } from "../js/store.js";

export default {
    name: "Search",
    data: () => ({
        store,
        apiUrl: "https://api.themoviedb.org/3/search/movie",
        searchedInput: ""
    }),
    methods: {
        getList() {
            axios.get(this.apiUrl, {
                params: {
                    api_key: "fd6c8d21185dd9ebbf4e3da065049532",
                    query: this.searchedInput
                }
            }).then(response => {
                this.store.list = response.data.results;
                this.searchedInput = "";
            });
        }
    }
}
</script>

<template>
    <!-- Search -->
    <div id="search">
        <input type="search" id="search-bar" class="form-control" placeholder="Search" v-model="searchedInput"
            @keyup.enter="getList">
        <button id="search-button" class="btn btn-primary" @click="getList">Search</button>
    </div>
</template>

<style lang="scss" scoped>
@use "../scss/partials/mixins.scss" as *;

#search {
    @include flex(row, nowrap);
    gap: 0.5rem;
}
</style>