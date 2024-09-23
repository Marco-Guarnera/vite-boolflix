<script>
export default {
    name: "ListItem",
    props: {
        title: {
            type: String,
            required: true
        },
        originalTitle: {
            type: String,
            required: true
        },
        originalLanguage: {
            type: String,
            required: true
        },
        voteAverage: {
            type: Number,
            required: true
        }
    }
}
</script>

<template>
    <!-- List Item -->
    <li class="list-item">
        <div v-text="title"></div>
        <div v-text="originalTitle"></div>
        <div v-text="originalLanguage"></div>
        <div v-text="voteAverage"></div>
    </li>
</template>

<style lang="scss" scoped></style>