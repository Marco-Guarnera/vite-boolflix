<script>
export default {
    name: "MoviesListItem",
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
    },
    data: () => ({
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
        }
    }
}
</script>

<template>
    <!-- Movies List Item -->
    <li class="movies-list-item">
        <div v-text="title"></div>
        <div v-text="originalTitle"></div>
        <div v-if="flagImgSrc === originalLanguage" v-text="originalLanguage"></div>
        <img v-else :src="flagImgSrc" :alt="title" class="flag">
        <div v-text="voteAverage"></div>
    </li>
</template>

<style lang="scss" scoped></style>