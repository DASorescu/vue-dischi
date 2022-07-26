<template>
    <main>
        <section class="albums h-100 container d-flex align-items-center ">
            <div class="discs-list row gy-3 gx-2">
                <div class="column p-4 " v-for="(disc, i) in discs" :key="i">
                    <DiscCard :image="disc.poster" :title="disc.title" :author="disc.author" :year="disc.year" />
                </div>
            </div>
        </section>
    </main>
</template>

<script>
import axios from 'axios';
import DiscCard from './DiscCard.vue';
export default {
    name: "TheMain",
    components: { DiscCard },
    data() {
        return {
            discs: [],
        };
    },
    mounted() {
        axios.get("https://flynn.boolean.careers/exercises/api/array/music").then((res) => {
            this.discs = res.data.response;
        });
    },
}
</script>

<style lang="scss">
@import'../assets/scss/vars';

main {
    color: #fff;
    background-color: $main_bg;
    height: 93vh;

    .column {
        width: calc(100% / 5 - 40px);
        margin: 10px 20px;
        background-color: $secondary_bg;
    }


}
</style>