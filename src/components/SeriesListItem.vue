<script>
export default {
    name: "SeriesListItem",
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
        },
        poster: {
            type: String,
            required: true
        }
    },
    data: () => ({
        imgWidth: "w342"
    }),
    computed: {
        flagImgSrc() {
            let imgName = "";
            switch (this.originalLanguage) {
                case "en":
                    imgName = "en.png";
                    break;
                case "it":
                    imgName = "it.png";
                    break;
                case "fr":
                    imgName = "fr.png";
                    break;
                case "es":
                    imgName = "es.png";
                    break;
                case "de":
                    imgName = "de.png";
                    break;
                default:
                    return this.originalLanguage;
            }
            return new URL(`../assets/img/${imgName}`, import.meta.url).href;
        },
        posterImgSrc() {
            return `https://image.tmdb.org/t/p/${this.imgWidth}/${this.poster}`;
        }
    }
}
</script>

<template>
    <!-- Series List Item -->
    <li class="series-list-item">
        <div v-text="title"></div>
        <div v-text="originalTitle"></div>
        <div v-if="flagImgSrc === originalLanguage" v-text="originalLanguage"></div>
        <img v-else :src="flagImgSrc" :alt="title" class="flag">
        <div v-text="voteAverage"></div>
        <img :src="posterImgSrc" :alt="title" class="poster">
    </li>
</template>

<style lang="scss" scoped></style>