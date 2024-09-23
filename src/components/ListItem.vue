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
    },
    data: () => ({
        imgName: ""
    }),
    computed: {
        imgSrc() {
            switch (this.originalLanguage) {
                case "en":
                    this.imgName = "en.png";
                    break;
                case "it":
                    this.imgName = "it.png";
                    break;
                case "fr":
                    this.imgName = "fr.png";
                    break;
                case "es":
                    this.imgName = "es.png";
                    break;
                case "de":
                    this.imgName = "de.png";
                    break;
                default:
                    this.imgName = this.originalLanguage;
                    break;
            }
            return new URL(`../assets/img/${this.imgName}`, import.meta.url).href;
        }
    }
}
</script>

<template>
    <!-- List Item -->
    <li class="list-item">
        <div v-text="title"></div>
        <div v-text="originalTitle"></div>
        <div v-if="imgName === originalLanguage" v-text="originalLanguage"></div>
        <img v-else :src="imgSrc" :alt="title">
        <div v-text="voteAverage"></div>
    </li>
</template>

<style lang="scss" scoped></style>