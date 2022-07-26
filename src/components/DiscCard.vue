<template>
    <div class="disc-card d-flex flex-column">
        <figure>
            <img :src="image" :alt="title" class="img-fluid">
        </figure>
        <div class="text-center">
            <h3 class="album-name mb-4">{{ title }}</h3>
            <p class="author m-0">{{ author }}</p>
            <p class="release-date m-0">{{ year }}</p>
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

p {
    color: #6F726D;
}
</style>