<template>
    <header class="d-flex align-items-center justify-content-between">
        <figure class=" h-100 m-0 d-flex justify-content-center align-items-center ">
            <img src="../assets/img/logo-small.svg" alt="Music" class="img-fluid">
        </figure>
        <OptionSelect class="mx-4" :generi="this.generi" @option-change="emitGenreChange" />
    </header>
</template>


<script>
import OptionSelect from './OptionSelect.vue';
export default {
    name: "BaseHeader",
    props: {
        generi: Array,
    },
    methods: {
        emitGenreChange(genre) {
            this.$emit('genre-change', genre)
        }
    },
    components: {

        OptionSelect
    },
}
</script>

<style  lang="scss" scoped>
@import'../assets/scss/vars';

header {

    height: 7vh;
    background-color: $secondary_bg;

    figure {
        width: 5%;

        img {
            padding-top: 5px;
            padding-bottom: 5px;
            height: 50px;
            width: 50px;
        }
    }
}
</style>
            
