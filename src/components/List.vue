<script>
import ListItem from "./ListItem.vue";
import { store } from "../js/store.js";

export default {
    name: "List",
    components: {
        ListItem
    },
    data: () => ({
        store
    })
}
</script>

<template>
    <!-- List -->
    <ul class="list">
        <!-- List Item -->
        <ListItem v-for="item in store.list" :key="item.id" :title="item.title" :original-title="item.original_title"
            :original-language="item.original_language" :vote-average="item.vote_average" />
    </ul>
</template>

<style lang="scss" scoped></style>