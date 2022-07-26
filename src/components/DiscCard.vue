<template>
    <div class="disc-card d-flex flex-column">
        <figure>
            <img :src="image" :alt="title" class="img-fluid">
        </figure>
        <div class="text-center">
            <h3 class="album-name">{{ title }}</h3>
            <p class="author">{{ author }}</p>
            <date class="release-date">{{ year }}</date>
        </div>
    </div>
</template>

<script>

export default {
    name: 'DiscCard',
    props: {
        image: String,
        title: String,
        author: String,
        year: String,

    }
}
</script>

<style lang="scss" scoped>
figure {
    height: 40%;
}
</style>