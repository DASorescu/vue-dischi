<template>
    <header>
        <figure class=" h-100 m-0 d-flex justify-content-center align-items-center ">
            <img src="../assets/img/logo-small.svg" alt="Music" class="img-fluid">
        </figure>
    </header>
</template>


<script>
export default {
    name: 'BaseHeader',
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
            
